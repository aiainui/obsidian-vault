# Kimi 最新论文总结

> 更新时间：2026-03-18

本文总结月之暗面（Moonshot AI）Kimi 团队近期发布的两项重要技术成果：

---

## 1. Attention Residuals (AttnRes) 架构

**论文标题：** Attention Residuals: Rethinking Depth-wise Aggregation

**arXiv:** [2603.15031](https://arxiv.org/abs/2603.15031)

**GitHub:** [MoonshotAI/Attention-Residuals](https://github.com/MoonshotAI/Attention-Residuals) (⭐ 1.3k Stars)

### 核心创新

**标准残差连接**以固定单位权重累积所有层输出，导致：
- 随着深度增长，每个层的贡献被稀释
- 隐藏状态幅度无限增长（PreNorm 的已知问题）

**AttnRes** 用**softmax注意力**替代固定累积：
$$\mathbf{h}_l = \sum_{i=0}^{l-1} \alpha_{i \to l} \cdot \mathbf{v}_i$$

其中权重 $\alpha_{i \to l}$ 通过每层学习的伪查询 $\mathbf{w}_l \in \mathbb{R}^d$ 计算，使每层能够**选择性、内容感知地**访问更早的表示。

### Block AttnRes

完整 AttnRes 在大规模时需要 O(Ld) 内存。**Block AttnRes** 将层划分为 N 个块，在块内使用标准残差累积，仅在块级表示上应用注意力。使用约 8 个块即可恢复大部分 AttnRes 收益，同时实际开销极小。

### 实验结果

#### 扩展定律
AttnRes 在所有计算预算下始终优于基线。Block AttnRes 达到与**多 1.25 倍计算量**训练的基线相同的损失。

#### 下游性能 (Kimi Linear 48B / 3B 激活, 1.4T tokens)

| 类别 | 基准 | 基线 | AttnRes |
|------|------|------|---------|
| General | MMLU | 73.5 | **74.6** |
| GPQA-Diamond | 36.9 | **44.4** (+7.5) |
| BBH | 76.3 | **78.0** |
| TriviaQA | 69.9 | **71.8** |
| Math | 53.5 | **57.1** |
| HumanEval | 59.1 | **62.2** (+3.1) |
| MBPP | 72.0 | **73.9** |
| Chinese | CMMLU | 82.0 | **82.9** |
| C-Eval | 79.6 | **82.5** |

**最大提升：** 多步推理（+7.5 on GPQA-Diamond）和代码生成（+3.1 on HumanEval）

### 训练动态
- 缓解 PreNorm 稀释问题
- 跨深度的输出幅度保持有界
- 梯度范数在层间更均匀分布

### 作者
Kimi Team + Chen, Guangyu / Zhang, Yu / Su, Jianlin / Xu, Weixin 等

---

## 2. Kimi K2.5 - 视觉型代理智慧

**发布时间：** 2026年1月27日

**特点：**
- **原生多模态能力**：支持视觉理解与推理
- **Agent Swarm（代理群）**：可自动生成并协调最多 **100 个子代理**
- **并行处理复杂任务**：群体智能协作架构

### 核心突破

K2.5 标志着 AI 产业从**单一代理架构**迈向**群体智能协作**的关键转折。

---

## 相关资源

- [Attention Residuals 论文 PDF](https://github.com/MoonshotAI/Attention-Residuals/blob/master/Attention_Residuals.pdf)
- [Kimi 开放平台](https://www.moonshot.cn/)
- [Moonshot AI GitHub](https://github.com/MoonshotAI)

---

*本文档由 AI 助手自动生成并同步至 Obsidian*
