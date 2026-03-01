# GameDevSkills

一个面向 AI Agent 的技能（Skill）库，收录可扩展能力的专项技能。

## Skills 列表

| Skill | 用途 |
|-------|------|
| [skill-creator](./Skills/skill-creator/SKILL.md) | 创建新 Skill、迭代优化现有 Skill、运行评测与基准测试、优化触发描述 |
| [tech-research](./Skills/tech-research/SKILL.md) | 执行系统化技术调研，涵盖技术选型、可行性分析、框架对比，输出结构化调研报告 |
| [find-skills](./Skills/find-skills/SKILL.md) | 在技能生态中搜索并安装可扩展 Agent 能力的技能包 |
| [excel-analysis](./Skills/excel-analysis/SKILL.md) | 分析 Excel 文件，支持透视表、图表生成与数据清洗 |
| [readme-sync](./Skills/readme-sync/SKILL.md) | 对比 Skills 目录与 README 列表，自动将新增或删除的 Skill 同步到 README |
| [setup-agents-md](./Skills/setup-agents-md/SKILL.md) | 为项目初始化 AGENTS.md 及配套子系统文档，为 AI 编码代理提供全局指令 |

## 使用方式

在支持 Skill 的 AI Agent 环境中，将本仓库中的 Skill 目录路径配置到 Agent 的技能路径下，Agent 会根据用户指令自动识别并调用对应 Skill。

## License

[MIT](./LICENSE)
