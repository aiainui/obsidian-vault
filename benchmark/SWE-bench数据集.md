# SWE-bench 数据集

## 什么是 SWE-bench

**SWE-bench** (Software Engineering Benchmark) 是普林斯顿大学发布的基准测试，用于评估大语言模型解决真实世界软件问题的能力。

- **任务**：给定一个代码库 + GitHub issue，让 AI 生成补丁（patch）来修复问题
- **数据来源**：来自真实 GitHub 仓库的问题（Django、SymPy、Flask 等）
- **评估方式**：运行 AI 生成的 patch，看是否能通过测试

## 数据集版本

| 版本 | 说明 |
|------|------|
| SWE-bench | 完整测试集 |
| SWE-bench Lite | 精选 300 道题，更快测试 |
| SWE-bench Verified | OpenAI 合作，500 道经真人验证可解决的问题 |
| SWE-bench Multimodal | 视觉软件领域版本 |

## 相关项目

- **SWE-agent** - 当前 SOTA 方案，用 AI 自己操作代码
- **SWE-smith** - 生成 SWE 训练数据的工具包
- **sb-cli** - 云端评估工具

## 影响力

- ICLR 2024 Oral
- 4.5k ⭐ | 796 Fork
- 被 OpenAI、Anthropic 等广泛用于评估 AI 编程能力

## 类似数据集

| 数据集 | 特点 |
|--------|------|
| HumanEval | OpenAI 的代码生成测试 |
| MBPP | 简单编程题 |
| APPS | Codeforces 等编程题 |
| CodeXGLUE | 多任务代码基准 |
| DS-1000 | 数据科学问题 |

## 对话记录 (2026-03-18)

**小邓**: 介绍下 swe-bench

**我**: [介绍了 SWE-bench 的基本信息、版本、相关项目]

**Alan**: 本质上这个跟 swe-bench一样

**我**: 解释了 SWE-bench 和 HumanEval/MBPP/APPS 的区别

**Alan**: 还有类似的数据集吗

**我**: 列出了 HumanEval、MBPP、APPS 等数据集及其区别

**Alan**: 本质一样的吧

**我**: 询问具体指哪个

**Alan**: 这个数据集为啥叫swe

**我**: SWE = Software Engineering，来自论文全称

---

*同步时间: 2026-03-19*
