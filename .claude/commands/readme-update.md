# 生成目录

扫描 vault 中的所有 Markdown 文件，按文件夹分组生成两级目录结构，并写入 README.md。

## 执行步骤

1. 使用 Glob 扫描所有 `.md` 文件（排除 README.md 本身）
2. 按文件夹分组
3. 生成两级目录结构：
   - Agents
   - Papers
4. 使用 Wiki-link 格式 `[[path]]`
5. 写入 README.md

## 输出格式

```markdown
# 我的 Obsidian 个人知识库

## 目录

### Agents
- [[Agents/xxx/xxx]]

### Papers
- [[Papers/xxx]]
```
