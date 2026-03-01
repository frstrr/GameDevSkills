---
name: readme-sync
description: 维护 GameDevSkills 的 README.md。按“先同步文件、再同步清单”的方式：先把本机 ~/.agents/skills 同步到仓库 Skills/（只增不删），再将变更反映到 README Skills 列表。用户说“更新 README”“同步 Skills”“刷新列表”“新增/安装 Skill 了”等时使用本 skill。
---

# readme-sync

维护 `GameDevSkills` 仓库的 `README.md`，确保 Skills 列表与 `Skills/` 目录保持一致，且每个 Skill 在 README 中只占一行。

## 约束与规则
- 默认只做“新增/更新”，不自动删除仓库 `Skills/` 中的文件
- README 中出现“目录不存在的 skill”属于潜在删除项：必须先向用户确认再移除条目
- README 中每个 skill 只占一行，避免重复登记（同名只保留一条）

## 操作流程

### 0) 同步 Skill 文件
在仓库根目录运行 `sync-skills.bat`，将本机 `~/.agents/skills`（Windows 通常为 `%USERPROFILE%\.agents\skills`）同步到仓库 `Skills/` 目录（只增不删）。

PowerShell：
```powershell
& ".\sync-skills.bat"
```

退出码处理：
- `0–7`：视为成功（0=无变化，1=有复制，3=新增+复制等）
- `≥ 8`：视为失败；提示用户检查 robocopy 输出并终止，不继续后续步骤

备注：如你的本机 skills 目录不在上述位置，请调整 `sync-skills.bat` 里的 `SRC` 变量。

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
