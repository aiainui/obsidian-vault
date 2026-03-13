---
uid: 2026-03-13-autoresearch-complete
tags: [autoresearch, karpathy, ai-agent, llm-training, architecture, optimizer]
author: 小邓
created: 2026-03-13
updated: 2026-03-13
---

# AutoResearch 完全指南

> 基于 Karpathy 的 [autoresearch](https://github.com/karpathy/autoresearch) 项目
> 
> 相关项目：[nanochat](https://github.com/karpathy/nanochat)

---

## 一、项目概述

### 1.1 一句话定位

让 AI Agent 自主进行 LLM 训练实验的框架 — 给予 Agent 一个单 GPU 训练环境，它会自动修改代码、训练模型、评估结果、决定是否保留改进，一夜之间完成数百次实验。

### 1.2 与 nanochat 的关系

**AutoResearch 是 nanochat 的"自动化实验分支"**

| 项目 | 定位 | Stars |
|------|------|-------|
| **nanochat** | 完整的 LLM 训练框架 | 47,480 |
| **AutoResearch** | nanochat 的自动化实验模块 | 28,830 |

nanochat 的 leaderboard 里已经记录了 AutoResearch 的实验结果：

```
| # | time | val_bpb | Description | Date |
|---|-------------|---------|-------------|------|
| 5 | 1.80 | 0.71808 | autoresearch round 1 | Mar 9 2026 |
```

---

## 二、整体架构

```
┌─────────────────────────────────────────────────────────────┐
│                     program.md (Agent 指令)                  │
│         定义实验流程、约束、输出格式、循环逻辑                    │
└─────────────────────┬───────────────────────────────────────┘
                      │ 读取
                      ▼
┌─────────────────────────────────────────────────────────────┐
│                      train.py (Agent 可编辑)                  │
├─────────────────────────────────────────────────────────────┤
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────────────┐ │
│  │   GPT Model │  │   Optimizer │  │  Training Loop       │ │
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

### 核心文件职责

| 文件 | 职责 | 谁能修改 |
|------|------|----------|
| `prepare.py` | 数据下载、BPE tokenizer 训练、数据加载器、评估函数 | ❌ 固定不变 |
| `train.py` | GPT 模型、Muon + AdamW 优化器、训练循环 | ✅ Agent 独占 |
| `program.md` | Agent 指令集（prompts） | ✅ 人类迭代 |

---

## 三、数据准备 (prepare.py)

### 3.1 常量定义

```python
MAX_SEQ_LEN = 2048       # 上下文长度
TIME_BUDGET = 300        # 5分钟硬限制
EVAL_TOKENS = 40 * 524288  # 评估用的 token 数
VOCAB_SIZE = 8192        # BPE 词表大小
```

### 3.2 为什么要训练 BPE Tokenizer？

从 HuggingFace 下载的是**原始文本**，不是 token IDs。模型只能处理数字，所以要把文本转成数字。

BPE (Byte Pair Encoding) 需要从数据中学习：
```
原始文本 → 统计字节对频率 → 合并最高频的字节对 → 重复
```

### 3.3 数据加载器 (Best-fit Packing)

100% 利用率，无 padding：
1. 每个序列以 BOS token 开始
2. 贪心算法：找能填满剩余空间的最长文档
3. 裁剪最短文档填满剩余空间

---

## 四、模型架构 (train.py)

### 4.1 配置类

```python
@dataclass
class GPTConfig:
    sequence_len: int = 2048
    vocab_size: int = 32768   # 4x 于 tokenizer 的 8192
    n_layer: int = 12
    n_head: int = 6
    n_kv_head: int = 6        # GQA
    n_embd: int = 768
    window_pattern: str = "SSSL"
```

### 4.2 核心创新：Value Residual (ResFormer)

交替层（奇数层）有 Value Embedding，通过可学习的门控动态注入：

```python
ve = self.value_embeds[str(i)](idx)  # 从 token id 提取
gate = 2 * torch.sigmoid(self.ve_gate(x[..., :32]))
v = v + gate.unsqueeze(-1) * ve
```

### 4.3 滑动窗口模式 (SSSL)

```
window_pattern = "SSSL"  # 4 层一循环

Layer 0-2: S (Sliding) → 窗口 1024 (局部)
Layer 3:    L (Full)    → 窗口 2048 (全文)
```

**显存对比**：
| 模式 | 计算复杂度 |
|------|----------|
| Full (L) | O(T²) ≈ 4M |
| Sliding (S) | O(T × W) ≈ 2M |

### 4.4 MLP (SwiGLU)

```python
x = F.relu(x).square()  # SwiGLU: SiLU(x) * x
```

---

## 五、优化器 (MuonAdamW)

### 5.1 为什么矩阵参数用 Muon？

**核心原因：矩阵是"结构化的"**

```
传统 AdamW: 把每个参数看成独立的标量
Muon:       把参数矩阵看成"正交基上的变换"
```

假设一个线性层权重 `nn.Linear(768, 768)`：
- **AdamW**：768×768 = 58.9万个参数**独立**更新
- **Muon**：保持矩阵的**秩**和**正交性**

### 5.2 分层学习率

| 参数类型 | 优化器 | 学习率 |
|---------|--------|-------|
| lm_head (输出层) | AdamW | 0.004 |
| embeddings | AdamW | 0.6 |
| 矩阵参数 (Q/K/V/O/MLP) | **Muon** | 0.04 |
| 标量参数 (lambdas) | AdamW | 0.5 |

### 5.3 Muon 怎么读？

**Muon** 读作 **/ˈmjuːɒn/**（MOO-on），重音在第一个音节。

---

## 六、评估指标

### 6.1 为什么用 BPB 而非 Perplexity？

**Perplexity 问题**：
$$PP = e^{loss}$$

- 不同词表大小的模型，loss 不可比
- 词表大 → 预测目标更细粒度 → loss 自然更低

**BPB (Bits Per Byte)**：
$$BPB = \frac{\text{total\_nats}}{\log(2) \times \text{total\_bytes}}$$

- 衡量"预测下一个字节的能力"
- 与 vocab size 无关

---

## 七、训练循环

### 7.1 5 分钟固定时间做什么？

```python
while True:
    loss = model(x, y)
    loss.backward()
    optimizer.step()
    
    if total_training_time >= TIME_BUDGET:  # 300秒
        break
```

### 7.2 能训练多少 epoch？

```
5分钟 tokens ≈ 500K
数据集总量 ≈ 400B (climbmix-400b)

5分钟 ≈ 1/8000 epoch
```

**设计哲学**：用数量换质量，1 小时 = 12 次实验，1 晚 = 100 次实验。

### 7.3 会抢占显卡吗？

**会的**。AutoResearch 会独占显卡。

---

## 八、关键设计决策

| 决策 | 理由 |
|------|------|
| 5 分钟固定时间 | 1) 不同架构可直接对比 2) 找最优配置 |
| 单一修改文件 | diff 可审查 |
| val_bpb 指标 | vocab-independent |
| 不提交 results.tsv | 避免污染 git 历史 |

---

## 九、相关链接

- [GitHub: karpathy/autoresearch](https://github.com/karpathy/autoresearch)
- [GitHub: karpathy/nanochat](https://github.com/karpathy/nanochat)
- [Karpathy 推文](https://x.com/karpathy/status/2029701092347630069)
