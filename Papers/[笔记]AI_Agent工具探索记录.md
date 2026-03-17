# AI Agent 工具探索记录

> 更新时间：2026-03-18

记录今日探索的 AI Agent 相关 GitHub 项目。

---

## 1. Context Hub

**仓库：** https://github.com/andrewyng/context-hub

**是什么：** AI 编程代理的文档工具

**核心功能：**
- 为 AI 代理提供版本化、精选的 API 文档
- 支持多语言（Python、JavaScript）
- Agent 本地标注笔记，跨会话记忆
- 使用反馈机制（up/down）帮助作者改进文档

**安装使用：**
```bash
npm install -g @aisuite/chub
chub search "stripe payments"
chub get stripe/api --lang js
```

**解决什么问题：**
- 编程代理会"幻觉" API 用法
- 每次会话都会忘记之前学到的知识

---

## 2. gstack

**仓库：** https://github.com/garrytan/gstack

**是什么：** Claude Code 工作流增强工具，把单一助手变成"专家团队"

**包含 13 个 slash 命令：**

| 命令 | 角色 | 功能 |
|------|------|------|
| `/plan-ceo-review` | CEO | 重新审视需求，找 10 星产品 |
| `/plan-eng-review` | 工程经理 | 锁定架构、数据流、测试 |
| `/plan-design-review` | 设计师 | 80 项设计审查，AI Slop 检测 |
| `/review` | 资深工程师 | 找生产会爆的 bug |
| `/ship` | 发布工程师 | 自动 sync、测试、推送、开 PR |
| `/browse` | QA | 登录点击截图自动化 |
| `/qa` | QA+修复 | 测试找 bug 修复验证 |
| `/qa-design-review` | 设计师+前端 | 审计设计并修复 |
| `/retro` | 工程经理 | 团队回顾 |
| `/document-release` | 技术文档 | 自动更新文档 |

**具体好处：**
1. 需求审查 — 避免做错东西
2. 代码质量 — 减少生产事故
3. 测试自动化 — 不用人工点点点
4. 发布标准化 — 一键上线
5. 设计一致性 — 告别 AI 风
6. 多线程并行 — 10 个 Claude Code 同时干活

**评价：** 把"断断续续的 AI 聊天"变成"工业级软件生产线"

---

## 3. erduo-skills

**仓库：** https://github.com/rookie-ricardo/erduo-skills

**是什么：** AI Agent 技能库，提供信息采集工作流

**包含技能：**

| 技能 | 功能 |
|------|------|
| 每日日报 | 自动抓取技术新闻，生成 Markdown 日报 |
| AK RSS Digest | 精选 RSS，7 分以上筛选，中文日报格式 |
| Gemini Watermark Remover | 去除 Gemini 图片水印 |

**架构：**
- Master-Worker 模式
- 智能调度（有早停机制）
- 无头浏览器支持

**问题记录：**
- RSS 脚本有 SSL 证书问题，很多源抓取失败

---

## 每日新闻任务

**状态：** 已配置

**内容：**
- 每天早上 8:00 自动抓取技术新闻
- 筛选高质量内容
- 通过飞书发送给用户

**原因：** erduo-skills 的 RSS 工具有 SSL 问题，改为直接用 AI 能力抓取
