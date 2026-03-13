---
uid: 2026-03-13-autoresearch-optimizer
tags: [autoresearch, karpathy, optimizer, muon]
author: 小邓
created: 2026-03-13
updated: 2026-03-13
---

# AutoResearch 优化器详解

> 来源：与 AI 助手（小邓）的对话

## Q1: 项目采用哪些优化器？

项目使用 **MuonAdamW**，一个混合优化器：

### 1. Muon — 结构化优化器

用于 **2D 矩阵参数**（Q/K/V/O/MLP 权重）

```python
# 核心算法
def muon_step_fused(stacked_grads, stacked_params, ...):
    # 1. Nesterov momentum
    # 2. Polar Express 正交化
    # 3. NorMuon 方差衰减
```

### 2. AdamW — 标准优化器

用于 **非矩阵参数**：

| 参数类型 | 优化器 | 学习率 |
|---------|--------|-------|
| lm_head (输出层) | AdamW | 0.004 |
| embeddings | AdamW | 0.6 |
| value embeddings | AdamW | 0.6 |
| 矩阵参数 (Q/K/V/O/MLP) | **Muon** | 0.04 |
| 标量参数 (lambdas) | AdamW | 0.5 |

### 3. 分层学习率设计

```python
param_groups = [
    dict(kind='adamw', params=lm_head_params, lr=0.004),
    dict(kind='adamw', params=embedding_params, lr=0.6),
    dict(kind='muon', params=matrix_params, lr=0.04),  # Muon
    dict(kind='adamw', params=scalar_params, lr=0.5),
]
```

---

## Q2: 为什么矩阵参数用 Muon？

### 核心原因：矩阵是"结构化"的

```
传统 AdamW: 把每个参数看成独立的标量
Muon:       把参数矩阵看成"正交基上的变换"
```

### 数学解释

**AdamW 更新**（每个参数独立）：
```
w = w - lr * (grad / √(v + ε) + wd * w)
```

**Muon 更新**（保持矩阵结构）：
```
1. 计算梯度矩阵 G
2. 把 G 正交化（投影到正交子空间）
3. 更新
```

### 为什么这对矩阵重要？

假设一个线性层权重：
```python
nn.Linear(768, 768)  # 参数形状 (768, 768)
```

- **AdamW**：把 768×768 = 589K 个参数**独立**更新
- **Muon**：保持矩阵的**秩**和**正交性**

### 直观理解

| 优化器 | 对矩阵的认知 |
|-------|------------|
| AdamW | 58.9万个独立数字 |
| Muon | 一个 768×768 的线性变换 |

**结果**：Muon 优化后的矩阵更有利于保持信息流（梯度在各层之间传递时不容易"坍塌"）。

### 论文依据

Muon 来自论文 **"Muon: A Scalable Optimizer for Matrix Neural Networks"**

核心思想：在大模型中，矩阵是最核心的参数形式（Attention 的 Q/K/V/O，MLP 的权重），用结构化优化能更好收敛。

---

## Q3: Muon 怎么读？

**Muon** 读作 **/ˈmjuːɒn/**（MOO-on）

- **英**: /ˈmjuːɒn/
- **美**: /ˈmuːɑːn/

重音在第一个音节，发音类似 "**木-昂**"。

**词源**：来自物理学的 **μ子** (muon)，一种基本粒子。

---

## 相关链接

- [GitHub: karpathy/autoresearch](https://github.com/karpathy/autoresearch)
