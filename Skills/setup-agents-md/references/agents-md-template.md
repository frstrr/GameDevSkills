# [项目名称]

> [一句话项目描述]

## 技术栈

- **引擎/框架**：[如 Unity 2022.3 LTS / Unreal 5.4 / React 18.3]
- **语言**：[如 C# / TypeScript / Python 3.12]
- **关键依赖**：[如 UniTask 2.5、DOTween、Addressables 1.21]
- **包管理**：[如 npm / pnpm / pip / NuGet]

## 核心命令

```bash
# 构建
[构建命令，如 dotnet build / npm run build]

# 运行
[运行命令，如 npm run dev / Unity Play Mode]

# 测试
[测试命令，如 npm run test / dotnet test / pytest -v]

# 代码检查
[lint 命令，如 npm run lint / dotnet format --check]

# 格式化
[格式化命令，如 npm run format / dotnet format]
```

## 项目结构

- [核心模块描述，如：游戏逻辑模块处理角色控制、战斗和关卡管理]
- [数据层描述，如：配置数据通过 Excel → Luban 生成 C# 类，运行时只读]
- [UI 模块描述，如：UI 使用 MVVM 架构，ViewModel 与 View 分离]
- [工具/编辑器扩展描述]

> 详细目录说明见 README.md

## 编码规范

### 命名约定
- 类名：PascalCase（如 `PlayerController`）
- 方法：PascalCase（如 `GetDamage()`）
- 私有字段：_camelCase（如 `_maxHealth`）
- 常量：UPPER_SNAKE_CASE（如 `MAX_PLAYER_COUNT`）
- 接口：I 前缀（如 `IRecyclable`）

### 架构模式
- [描述项目使用的关键模式，如：使用对象池管理所有可复用对象]
- [描述通信模式，如：系统间通过事件总线通信，禁止直接引用]

### 代码范式

```[语言]
// 展示项目的关键编码范式
// 如：所有配置从配置表读取、对象池回收接口、Manager 单例模式等
[在此放置 1 个关键代码范式，约 15-25 行]
```

## 权限边界

### 始终可以（无需确认）
- 读取文件、列出目录
- 运行 lint / format / 单个文件的类型检查
- 运行单个测试用例

### 先问再做
- 安装/升级依赖包
- 删除文件或目录
- 运行完整构建或端到端测试套件
- git push / 创建分支

### 绝对禁止
- 提交密钥、凭证、API Key 到版本控制
- 修改生产环境或线上配置
- 在游戏逻辑中硬编码数值（所有数值从配置表读取）
- 单个文件超过 300 行（拆分为更小的模块）
- [根据项目添加更多禁止项]

## Git 工作流

- 主分支：`main`（受保护，禁止直接 push）
- 开发分支命名：`feature/[功能名]`、`fix/[问题描述]`
- 提交信息格式：`[类型]: [描述]`（如 `feat: 实现蓄力跳跃`）
- 每次提交前运行 lint 和测试

## 子系统文档

> 各子系统的详细设计和任务文档：

- [子系统1 文档路径和描述]
- [子系统2 文档路径和描述]
- [子系统3 文档路径和描述]
