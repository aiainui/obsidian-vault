---
uid: 2026-03-13
tags: [autoresearch, karpathy, ai-agent, llm-training, architecture]
author: 小邓
created: 2026-03-13
updated: 2026-03-13
---

# AutoResearch 架构深度解读

> 基于 Karpathy 的 [autoresearch](https://github.com/karpathy/autoresearch) 项目

## 整体架构

```
┌─────────────────────────────────────────────────────────────┐
│                     program.md (Agent 指令)                  │
│         定义实验流程、约束、输出格式、循环逻辑                  │
└─────────────────────┬───────────────────────────────────────┘
                      │ 读取
                      ▼
┌─────────────────────────────────────────────────────────────┐
│                      train.py (Agent 可编辑)                  │
├─────────────────────────────────────────────────────────────┤
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────────────┐ │
│  │   GPT Model │  │   Optimizer │  │  Training Loop      │ │
│  │ (Transformer)│  │ (Muon/AdamW)│  │ (5min time budget)  │ │
│  └─────────────┘  └─────────────┘  └─────────────────────┘ │
│  - Attention: 滑动窗口 + Value Residual                      │
│  - MLP: SwiGLU                                               │
│  - RMSNorm                                                   │
└─────────────────────┬───────────────────────────────────────┘
                      │ 训练
                      ▼
┌─────────────────────────────────────────────────────────────┐
│              evaluate_bpb() ← prepare.py 提供                │
│         评估 val_bpb (validation bits per byte)              │
└─────────────────────────────────────────────────────────────┘
```

## 核心文件职责

### 1. `prepare.py` — 不可变的基座

```python
# 关键常量
MAX_SEQ_LEN = 2048      # 上下文长度
TIME_BUDGET = 300        # 5分钟硬限制
EVAL_TOKENS = 40 * 524288  # 评估 token 数
VOCAB_SIZE = 8192        # BPE vocab 大小

# 核心函数（Agent 调用）
Tokenizer          # BPE 分词器
make_dataloader()  # 数据加载器
evaluate_bpb()     # 评估函数（唯一真值）
```

**设计意图**：把"不变的部分"全部固化，Agent 只关注 `train.py` 的改动，避免改坏评估基准。

### 2. `train.py` — Agent 的游乐场

#### 模型架构

```python
@dataclass
class GPTConfig:
    sequence_len: int = 2048
    vocab_size: int = 32768    # 4x vocab（相比 prepare 的 8192）
    n_layer: int = 12
    n_head: int = 6
    n_kv_head: int = 6         # GQA
    n_embd: int = 768
    window_pattern: str = "SSSL"  # 滑动窗口模式
```

#### 核心创新：Value Residual (ResFormer)

```python
class CausalSelfAttention(nn.Module):
    def __init__(self, config, layer_idx):
        # ...
        self.ve_gate = nn.Linear(self.ve_gate_channels, self.n_kv_head, 
                                 bias=False) if has_ve(layer_idx, config.n_layer) else None
    
    def forward(self, x, ve, cos_sin, window_size):
        # Value Residual: 输入相关的门控
        if ve is not None:
            gate = 2 * torch.sigmoid(self.ve_gate(x[..., :self.ve_gate_channels]))
            v = v + gate.unsqueeze(-1) * ve
```

**关键点**：交替层（奇数层）有 Value Embedding，通过可学习的门控动态注入。

#### 注意力模式：SSSL

```python
window_pattern: str = "SSSL"  # 4 种模式
# S = Sliding window (局部)
# L = Full attention (全局)
# "SSSL" = 3 层局部 + 1 层全局（交替）
```

### 3. `program.md` — Agent 的"灵魂"

这是项目的精髓：**不写死代码，而是写 prompt**

```markdown
## 实验循环
LOOP FOREVER:
1. 查看 git 状态
2. 修改 train.py
3. git commit
4. 运行: uv run train.py > run.log
5. 读取 val_bpb 结果
6. 记录到 results.tsv
7. 改进则保留，退步则回滚
```

**Agent 行为约束**：
- ✅ 可以改模型架构、超参数、优化器
- ❌ 不能改 prepare.py
- ❌ 不能装新包
- ❌ 不能问人类"要不要继续"

---

## 模块一：数据准备 (`prepare.py`)

### 1.1 常量定义

```python
MAX_SEQ_LEN = 2048       # 上下文长度
TIME_BUDGET = 300        # 5分钟硬限制
EVAL_TOKENS = 40 * 524288  # 评估用的 token 数
VOCAB_SIZE = 8192        # BPE 词表大小
```

**设计意图**：这些是"不变常量"，Agent 不能改，确保所有实验可对比。

### 1.2 数据下载

```python
BASE_URL = "https://huggingface.co/datasets/karpathy/climbmix-400b-shuffle/resolve/main"
MAX_SHARD = 6542  # 共 6543 个 shard
VAL_SHARD = MAX_SHARD  # 最后一个 shard 固定为验证集
```

- 从 HuggingFace 下载 `climbmix-400b-shuffle` 数据集
- 6542 个训练 shard + 1 个固定验证 shard
- 多进程并行下载，默认 8 workers

### 1.3 BPE Tokenizer 训练

```python
# 使用 rustbpe 加速（Rust 实现）
tokenizer = rustbpe.Tokenizer()
tokenizer.train_from_iterator(text_iterator(), vocab_size_no_special, pattern=SPLIT_PATTERN)

# 转为 tiktoken 格式保存
enc = tiktoken.Encoding(pat_str=pattern, mergeable_ranks=mergeable_ranks, ...)
```

**关键**：GPT-4 风格的 BPE 模式（`\p{N}{1,2}` 而非 `{1,3}`），对数字更友好。

### 1.4 数据加载器 (Best-fit Packing)

```python
def make_dataloader(tokenizer, B, T, split):
    """
    BOS-aligned dataloader with best-fit packing.
    100% 利用率，无 padding
    """
```

**核心算法**：
1. 每个序列以 BOS token 开始
2. 贪心算法：找能填满剩余空间的最长文档
3. 若无文档能完全放入，裁剪最短文档填满剩余空间
4. 100% token 利用率（无 padding waste）

### 1.5 评估函数 (val_bpb)

```python
@torch.no_grad()
def evaluate_bpb(model, tokenizer, batch_size):
    """
    Bits per byte (BPB): vocab size-independent 评估指标
    BPB = total_nats / (log(2) * total_bytes)
    """
```

**为什么用 BPB？**
- 与 vocab size 无关
- 不同词表大小的模型可直接对比
- 评估 40M tokens (约 2GB 文本)

---

## 模块二：模型架构 (`train.py` - GPT Model)

### 2.1 配置类

```python
@dataclass
class GPTConfig:
    sequence_len: int = 2048
    vocab_size: int = 32768   # 4x 于 tokenizer 的 8192
    n_layer: int = 12
    n_head: int = 6
    n_kv_head: int = 6        # GQA: KV heads = Q heads
    n_embd: int = 768
    window_pattern: str = "SSSL"
```

### 2.2 旋转位置编码 (RoPE)

```python
def apply_rotary_emb(x, cos, sin):
    """RoPE: 旋转_query和_key"""
    d = x.shape[3] // 2
    x1, x2 = x[..., :d], x[..., d:]
    y1 = x1 * cos + x2 * sin
    y2 = x1 * (-sin) + x2 * cos
    return torch.cat([y1, y2], 3)
```

**预计算**：
```python
cos, sin = self._precompute_rotary_embeddings(self.rotary_seq_len, head_dim)
# rotary_seq_len = sequence_len * 10 = 20480
```

### 2.3 注意力机制 (CausalSelfAttention)

```python
class CausalSelfAttention(nn.Module):
    def __init__(self, config, layer_idx):
        # GQA: 共享 KV 投影
        self.c_q = nn.Linear(n_embd, n_head * head_dim)
        self.c_k = nn.Linear(n_embd, n_kv_head * head_dim)
        self.c_v = nn.Linear(n_embd, n_kv_head * head_dim)
        
        # Value Residual (ResFormer)
        self.ve_gate = nn.Linear(ve_gate_channels, n_kv_head) if has_ve(...) else None
```

**关键创新：Value Residual**
```python
def forward(self, x, ve, cos_sin, window_size):
    # 提取 Value Embedding
    if ve is not None:
        gate = 2 * torch.sigmoid(self.ve_gate(x[..., :self.ve_gate_channels]))
        v = v + gate.unsqueeze(-1) * ve  # 门控残差连接
```

- 交替层有 Value Embedding（通过 vocab embedding 投影得到）
- 门控机制动态控制注入强度

### 2.4 滑动窗口模式 (SSSL)

```python
window_pattern: str = "SSSL"  # 4 种模式

# "SSSL" = 3 层 Sliding Window + 1 层 Full Attention
# S = 1024 (half context)
# L = 2048 (full context)
```

### 2.5 MLP (SwiGLU)

```python
class MLP(nn.Module):
    def forward(self, x):
        x = self.c_fc(x)           # up-projection
        x = F.relu(x).square()     # SwiGLU: SiLU(x) * x = relu(x)^2
        x = self.c_proj(x)         # down-projection
        return x
```

### 2.6 完整前向传播

```python
def forward(self, idx, targets=None):
    x = self.transformer.wte(idx)  # token embedding
    x = norm(x)
    x0 = x                         # 残差基线
    
    for i, block in enumerate(self.transformer.h):
        x = self.resid_lambdas[i] * x + self.x0_lambdas[i] * x0  # 动态残差权重
        ve = self.value_embeds[str(i)](idx) if str(i) in self.value_embeds else None
        x = block(x, ve, cos_sin, self.window_sizes[i])
    
    # LM Head with softcap
    logits = self.lm_head(x)
    logits = softcap * torch.tanh(logits / softcap)  # softcap = 15
```

**动态残差权重**：
- `resid_lambdas`: 每层可学习的残差系数（默认 1.0）
- `x0_lambdas`: 每层可学习的原始输入系数（默认 0.1）

---

## 模块三：优化器 (MuonAdamW)

这是项目最复杂部分，结合了两种优化器：

### 3.1 Muon — 结构化优化器

```python
@torch.compile
def muon_step_fused(stacked_grads, stacked_params, ...):
    # 1. Nesterov momentum
    momentum = momentum_t.to(stacked_grads.dtype)
    momentum_buffer.lerp_(stacked_grads, 1 - momentum)
    g = stacked_grads.lerp_(momentum_buffer, momentum)
    
    # 2. Polar Express 正交化
    X = g.bfloat16() / (X.norm(dim=(-2, -1), keepdim=True) * 1.02 + 1e-6)
    for a, b, c in polar_express_coeffs[:ns_steps]:
        A = X @ X.mT
        B = b * A + c * (A @ A)
        X = a * X + B @ X
    
    # 3. NorMuon 方差衰减
    v_mean = g.float().square().mean(dim=red_dim, keepdim=True)
    ...
```

**原理**：
- 将梯度投影到正交子空间（利于学习线性无关的特征）
- 类似于 Riemannian 优化但在矩阵流形上

### 3.2 分层学习率

```python
def setup_optimizer(self, ...):
    param_groups = [
        dict(kind='adamw', params=lm_head_params, lr=unembedding_lr),    # 0.004
        dict(kind='adamw', params=embedding_params, lr=embedding_lr),    # 0.6
        dict(kind='adamw', params=value_embeds_params, lr=embedding_lr), # 0.6
        dict(kind='muon', params=matrix_params, lr=matrix_lr),          # 0.04
        dict(kind='adamw', params=scalar_params, lr=scalar_lr),          # 0.5
    ]
```

| 参数类型 | 学习率 | 优化器 |
|---------|--------|-------|
| lm_head (输出层) | 0.004 | AdamW |
| embeddings | 0.6 | AdamW |
| 矩阵参数 (Q/K/V/O/MLP) | 0.04 | Muon |
| 标量参数 (lambdas) | 0.5 | AdamW |

---

## 模块四：训练超参数

```python
# 模型架构
ASPECT_RATIO = 64        # model_dim = depth * 64
HEAD_DIM = 128           # attention head 维度
WINDOW_PATTERN = "SSSL"  # 滑动窗口模式
DEPTH = 8                # 层数 → n_embd = 8 * 64 = 512 (实际对齐到 128 的倍数)

# 优化
TOTAL_BATCH_SIZE = 2**19  # ~524K tokens/step
DEVICE_BATCH_SIZE = 128    # 单 GPU batch
WEIGHT_DECAY = 0.2         # Muon 专用
```

**计算**：
```
tokens_per_step = 128 * 2048 = 262,144
grad_accum_steps = 524,288 / 262,144 = 2
```

---

## 模块五：训练循环

```python
while True:
    # 1. 前向 + 反向传播
    for micro_step in range(grad_accum_steps):
        with autocast_ctx:  # bf16
            loss = model(x, y)
        loss = loss / grad_accum_steps
        loss.backward()
    
    # 2. 学习率调度
    progress = total_training_time / TIME_BUDGET
    lrm = get_lr_multiplier(progress)  # warmup + warmdown
    
    # 3. 优化器更新
    optimizer.step()
    model.zero_grad(set_to_none=True)
    
    # 4. 快速失败检测
    if math.isnan(train_loss_f) or train_loss_f > 100:
        print("FAIL")
        exit(1)
    
    # 5. 时间预算检查
    if step > 10 and total_training_time >= TIME_BUDGET:
        break
```

### 学习率调度

```python
def get_lr_multiplier(progress):
    if progress < WARMUP_RATIO:           # 0%
        return progress / WARMUP_RATIO    # 线性 warmup
    elif progress < 1.0 - WARMDOWN_RATIO: # 50%
        return 1.0                         # 恒定
    else:                                  # 50%-100%
        cooldown = (1.0 - progress) / WARMDOWN_RATIO
        return cooldown * 1.0 + (1 - cooldown) * FINAL_LR_FRAC  # 线性衰减到 0
```

---

## 模块六：评估与输出

```python
# 最终评估
val_bpb = evaluate_bpb(model, tokenizer, DEVICE_BATCH_SIZE)

# 输出
print(f"val_bpb:          {val_bpb:.6f}")
print(f"training_seconds: {total_training_time:.1f}")
print(f"peak_vram_mb:     {peak_vram_mb:.1f}")
print(f"mfu_percent:      {mfu:.2f}")      # Model FLOPs Utilization
print(f"total_tokens_M:   {total_tokens / 1e6:.1f}")
print(f"num_params_M:     {num_params / 1e6:.1f}")
```

---

## 关键设计决策

| 决策 | 理由 |
|------|------|
| 5 分钟固定时间 | 1) 不同架构可直接对比 2) 找最优配置而非最优模型 |
| 单一修改文件 | diff 可审查，避免"改坏找不到原因" |
| val_bpb 指标 | vocab-independent，架构变化可比 |
| 不提交 results.tsv | 避免污染 git 历史 |

## 为什么这样设计？

Karpathy 想验证：**"给 AI 一个最小实验环境，它能自主发现训练技巧吗？"**

- 极简代码 = 人类可读可理解
- 极简接口 = Agent 可操作
- 固定目标 = 优化 val_bpb

这是 AI 研究自动化的 "Hello World"。

---

## 相关链接

- [GitHub: karpathy/autoresearch](https://github.com/karpathy/autoresearch)
- [nanochat](https://github.com/karpathy/nanochat)
- [Karpathy 推文](https://x.com/karpathy/status/2029701092347630069)
