# 生成目录

扫描 vault 中的文件夹结构，生成两级目录（只显示到二级目录），并写入 README.md。

## 执行步骤

1. 扫描顶层的文件夹（一级目录）
2. 对每个一级目录进行处理：
   - 如果该目录下有子文件夹/文件：
     - 在该目录下创建 README.md，列出其内容
     - 主 README.md 中使用 `[[path/README|display name]]` 格式链接
   - 如果该目录下只有单个文件：
     - 直接链接到该文件 `[[path/file]]`
3. Papers 目录只列出文件
4. 使用 Wiki-link 格式
5. 写入 README.md

## 关键要求

- **重要**：Wiki-link 无法直接链接到文件夹，必须链接到文件夹内的 README.md
- 对于有内容的文件夹，创建 `README.md` 并链接到它
- 使用 `[[path/README|display name]]` 格式可自定义显示名称

## 输出格式

```markdown
### Agents
- [[Agents/SocialKit/README|SocialKit]]
- [[Agents/claude code/README|Claude Code]]
- [[Agents/travily介绍]]

### Papers
- [[Papers/[笔记]DeepAgent_2510.21618v3]]
```

## 排序规则

- Agents 始终放在最前面
- 按字母顺序排列
