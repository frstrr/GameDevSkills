# GameDevSkills

一个面向 AI Agent 的技能（Skill）库，收录可扩展能力的专项技能。

## Skills 列表

| Skill | 用途 |
|-------|------|
| [skill-creator](./Skills/skill-creator/SKILL.md) | 创建新 Skill、迭代优化现有 Skill、运行评测与基准测试、优化触发描述 |
| [tech-research](./Skills/tech-research/SKILL.md) | 执行系统化技术调研，涵盖技术选型、可行性分析、框架对比，输出结构化调研报告 |
| [readme-sync](./Skills/readme-sync/SKILL.md) | 对比 Skills 目录与 README 列表，自动将新增或删除的 Skill 同步到 README |

## 使用方式

在支持 Skill 的 AI Agent 环境中，将本仓库中的 Skill 目录路径配置到 Agent 的技能路径下，Agent 会根据用户指令自动识别并调用对应 Skill。

## License

[MIT](./LICENSE)
