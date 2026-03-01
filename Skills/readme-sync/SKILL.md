---
name: readme-sync
description: 维护 GameDevSkills 仓库的 README.md，将新增或变更的 Skill 同步到 Skills 列表。当用户说"更新 README"、"同步 Skills 列表"、"我添加了新的 Skill"、"刷新库"等时，使用本 skill。
---

# readme-sync

维护 `GameDevSkills` 仓库的 `README.md`，确保 Skills 列表与 `Skills/` 目录保持一致。

## 流程

### 第一步：读取现状

并行执行以下两件事：
1. 读取 `README.md`，提取当前 Skills 列表（表格或分组标题下的条目）中已登记的所有 Skill 名称
2. 列出 `Skills/` 目录下的所有子目录，读取每个子目录的 `SKILL.md` frontmatter，获取 `name` 和 `description`

### 第二步：对比差异

- **新增**：在 `Skills/` 目录中存在但 README 中未登记的 Skill
- **已删除**：README 中有记录但 `Skills/` 目录中已不存在的 Skill（提示用户确认后再从 README 移除）
- **无变化**：跳过

### 第三步：更新 README

**新增条目格式**（每个 Skill 占一行）：
```
| [skill-name](./Skills/skill-name/SKILL.md) | 一句话用途描述 |
```

用途描述的写法：
- 来源优先级：① SKILL.md 的 `description` 字段提炼 → ② SKILL.md 正文第一句
- 控制在 30 字以内，说清楚"能做什么"，不展开细节
- 使用中文

**插入位置**：
- 如果 README 中已有分类标题（如 `### 工具类`），根据 Skill 的用途判断归属，插入对应分类的表格末尾
- 如果尚无分类，直接追加到现有表格末尾

**移除条目**：经用户确认后，删除对应行。

### 第四步：汇报

告知用户：新增了哪些 Skill、移除了哪些（如有）、哪些保持不变。
