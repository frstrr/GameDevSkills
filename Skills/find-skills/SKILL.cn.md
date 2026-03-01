# 查找技能

该技能用于从开放的智能体技能生态中发现并安装技能。

## 何时使用该技能

在以下情况使用本技能：

- 用户问“如何做 X”，而 X 可能是已有技能能覆盖的常见任务
- 用户说“帮我找一个做 X 的技能”或“有没有做 X 的技能”
- 用户问“你能做 X 吗”，而 X 是一个专业能力
- 用户表达希望扩展智能体能力
- 用户想搜索工具、模板或工作流
- 用户提到需要某个领域的帮助（设计、测试、部署等）

## 什么是 Skills CLI？

Skills CLI（`npx skills`）是开放智能体技能生态的包管理器。技能是模块化包，可用专业知识、工作流和工具扩展智能体能力。

**关键命令：**

- `npx skills find [query]` - 交互式或按关键词搜索技能
- `npx skills add <package>` - 从 GitHub 或其他来源安装技能
- `npx skills check` - 检查技能更新
- `npx skills update` - 更新所有已安装技能

**浏览技能：** https://skills.sh/

## 如何帮助用户找到技能

### 第一步：理解需求

当用户请求帮助时，识别：

1. 领域（如 React、测试、设计、部署）
2. 具体任务（如编写测试、制作动画、审查 PR）
3. 这是否足够常见，因而可能已有技能

### 第二步：搜索技能

使用相关查询运行查找命令：

```bash
npx skills find [query]
```

例如：

- 用户问“如何让我的 React 应用更快？” → `npx skills find react performance`
- 用户问“你能帮我做 PR 审查吗？” → `npx skills find pr review`
- 用户问“我需要生成 changelog” → `npx skills find changelog`

该命令会返回类似结果：

```
Install with npx skills add <owner/repo@skill>

vercel-labs/agent-skills@vercel-react-best-practices
└ https://skills.sh/vercel-labs/agent-skills/vercel-react-best-practices
```

### 第三步：向用户呈现选项

找到相关技能后，向用户提供：

1. 技能名称及其功能
2. 用户可运行的安装命令
3. skills.sh 上的详情链接

示例回复：

```
我找到一个可能有帮助的技能！“vercel-react-best-practices” 提供
来自 Vercel Engineering 的 React 与 Next.js 性能优化指南。

安装命令：
npx skills add vercel-labs/agent-skills@vercel-react-best-practices

了解更多：https://skills.sh/vercel-labs/agent-skills/vercel-react-best-practices
```

### 第四步：主动提出安装

如果用户愿意继续，你可以替他们安装技能：

```bash
npx skills add <owner/repo@skill> -g -y
```

`-g` 表示全局（用户级）安装，`-y` 用于跳过确认提示。

## 常见技能分类

搜索时可参考以下常见分类：

| 类别     | 示例查询                          |
| -------- | --------------------------------- |
| Web 开发 | react, nextjs, typescript, css, tailwind |
| 测试     | testing, jest, playwright, e2e    |
| DevOps   | deploy, docker, kubernetes, ci-cd |
| 文档     | docs, readme, changelog, api-docs |
| 代码质量 | review, lint, refactor, best-practices |
| 设计     | ui, ux, design-system, accessibility |
| 效率     | workflow, automation, git         |

## 有效搜索的技巧

1. **使用具体关键词**：“react testing” 比 “testing” 更好
2. **尝试替换词**：如果 “deploy” 没结果，试试 “deployment” 或 “ci-cd”
3. **关注常见来源**：许多技能来自 `vercel-labs/agent-skills` 或 `ComposioHQ/awesome-claude-skills`

## 未找到技能时

如果没有相关技能：

1. 说明未找到现有技能
2. 说明你仍可直接帮助完成任务
3. 建议用户用 `npx skills init` 创建自己的技能

示例：

```
我搜索了与 “xyz” 相关的技能，但没有找到匹配结果。
我仍然可以直接帮你完成这个任务！要继续吗？

如果这是你经常需要的内容，可以创建自己的技能：
npx skills init my-xyz-skill
```
