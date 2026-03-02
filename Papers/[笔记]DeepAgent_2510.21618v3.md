# DeepAgent: A General Reasoning Agent with Scalable Toolsets

## 基本信息
- **标题**: DeepAgent: A General Reasoning Agent with Scalable Toolsets
- **作者**: Xiaoxi Li, Wenxiang Jiao, Jiarui Jin, Guanting Dong, Jiajie Jin, Yinuo Wang, Hao Wang, Yutao Zhu, Ji-Rong Wen, Yuan Lu, Zhicheng Dou
- **机构**: RUC-NLPIR (中国人民大学)
- **arXiv ID**: 2510.21618v3
- **PDF链接**: [[DeepAgent_2510.21618v3.pdf]]
- **在线链接**: https://arxiv.org/abs/2510.21618v3
- **发表**: WWW 2026
- **下载日期**: 2026-03-02

## 摘要
大型推理模型已展现出强大的问题解决能力，但现实世界任务通常需要外部工具和长期交互。现有的Agent框架通常遵循预定义的工作流程，限制了自主和全局任务完成。本文提出DeepAgent，一个端到端的深度推理Agent，在单一连贯的推理过程中执行自主思考、工具发现和动作执行。

## 核心贡献
1. **端到端深度推理Agent** - 在单一推理过程中完成自主思考、工具发现和执行
2. **自主记忆折叠机制** - 将过去的交互压缩为结构化的情景记忆、工作记忆和工具记忆
3. **ToolPO强化学习策略** - 利用LLM模拟的API并应用工具调用优势分配

## 主要方法

### 1. 自主记忆折叠机制
- **情景记忆(Episodic Memory)**: 压缩长期交互历史
- **工作记忆(Working Memory)**: 保留当前任务关键信息
- **工具记忆(Tool Memory)**: 存储可用工具知识
- 减少错误累积同时保留关键信息

### 2. ToolPO 强化学习
- LLM模拟API
- 工具调用优势分配
- 细粒度信用分配给工具调用token

## 实验结果

### 评测基准(8个)
- **通用工具使用任务**: ToolBench, API-Bank, TMDB, Spotify, ToolHop
- **下游应用**: ALFWorld, WebShop, GAIA, HLE

### 性能表现
- 在labeled-tool和open-set tool retrieval场景下均优于baseline

## 关键创新点
1. 端到端推理Agent，统一思考-工具发现-执行流程
2. 记忆折叠机制解决长程交互问题
3. ToolPO无需人工标注的强化学习训练

## 局限性
- 需要大量计算资源训练
- 工具库规模受限于LLM能力

## 个人笔记

### 应用场景
- 自动化工作流
- 复杂任务规划
- 多工具协调

### 启发
- 记忆机制对长程任务很重要
- 端到端训练比手工设计更灵活

### 相关工作
- ToolBench
- API-Bank
- ReAct
- Reflexion

## 引用
```bibtex
@article{deepagent2025,
  title={DeepAgent: A General Reasoning Agent with Scalable Toolsets},
  author={Li, Xiaoxi and Jiao, Wenxiang and Jin, Jiarui and Dong, Guanting and Jin, Jiajie and Wang, Yinuo and Wang, Hao and Zhu, Yutao and Wen, Ji-Rong and Lu, Yuan and Dou, Zhicheng},
  journal={arXiv preprint arXiv:2510.21618},
  year={2025}
}
```

## 标签
#AI #Agent #Reasoning #Toolsets #DeepAgent #WWW2026 #RUC
