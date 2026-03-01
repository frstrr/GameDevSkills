---
name: readme-sync
description: 维护 GameDevSkills 的 README.md，将 Skills/ 下新增或变更的 Skill 同步到 Skills 列表。当用户说“更新 README”“同步 Skills 列表”“新增 Skill 了”“刷新库”等时使用本 skill。
---

# readme-sync

维护 `GameDevSkills` 仓库的 `README.md`，确保 Skills 列表与 `Skills/` 目录保持一致，且每个 Skill 在 README 中只占一行。

## 操作流程

### 1) 读取现状
并行完成：
- 读取 `README.md`，提取 Skills 列表中已登记的 Skill 名称
- 遍历 `Skills/` 目录子文件夹，读取每个 `SKILL.md` frontmatter 的 `name` 和 `description`

### 2) 对比差异
- **新增**：目录中存在但 README 未记录
- **已删除**：README 有记录但目录不存在（先向用户确认再移除）
- **无变化**：跳过

### 3) 更新 README
新增条目格式（每个 Skill 一行）：
```
| [skill-name](./Skills/skill-name/SKILL.md) | 一句话用途描述 |
```

用途描述规则：
- 优先从 `description` 提炼，不可超过 30 字
- 中文、只说用途、不展开细节

插入位置：
- 若 README 已按分类分组，则插入对应分类表格末尾
- 否则直接追加到现有表格末尾

### 4) 汇报变更
说明新增/移除的 Skill 与更新原因。
