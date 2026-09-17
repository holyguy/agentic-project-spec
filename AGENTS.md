# [PROJECT_NAME] — Agent 开发规范

<!-- 
  本文件是所有 AI Agent 的统一规则入口。
  支持的 Agent: Claude Code, Codex, OpenCode, Antigravity, CodeBuddy
  各 Agent 专属配置见同目录下对应的 .md 文件。
-->

## 项目概述

<!-- TODO: 填写项目描述 -->
[项目名称] 是一个 [项目描述]，面向 [目标用户]。

## 技术栈

当前使用的技术栈预设见 `stacks/` 目录。
可选预设：react-typescript / vue-typescript / nextjs / python-fastapi / go-gin

<!-- TODO: 确认技术栈后取消注释对应行 -->
<!-- 当前预设: react-typescript + python-fastapi -->

## 关键命令

| 操作 | 命令 |
|:-----|:-----|
| 安装依赖 | `pnpm install` |
| 开发服务器 | `pnpm dev` |
| 运行测试 | `pnpm test` |
| 代码检查 | `pnpm lint` |
| 类型检查 | `pnpm typecheck` |
| 构建 | `pnpm build` |

## 编码规范

→ 详细规范见 [.agents/rules/coding-standards.md](.agents/rules/coding-standards.md)

核心要点：
- 变量/函数: camelCase，类/组件: PascalCase，常量: UPPER_SNAKE_CASE
- 文件/文件夹: kebab-case
- 注释解释「为什么」而非「是什么」
- 所有函数必须标注类型

## 设计体系

→ 生成 UI 组件前**必须**读取 [DESIGN.md](DESIGN.md)
→ 设计风格预设见 `.stitch/presets/` 目录

## 架构约束

→ 系统架构见 [docs/ARCHITECTURE.md](docs/ARCHITECTURE.md)
→ 领域模型见 [docs/CONTEXT.md](docs/CONTEXT.md)
→ 架构决策记录见 [docs/ADR/](docs/ADR/)

### 分层原则（后端）

| 层级 | 职责 |
|:-----|:-----|
| api | 请求解析与响应封装 |
| service | 业务逻辑处理 |
| repository | 数据库访问 |
| schema | 请求/响应数据校验 |
| model | ORM 模型定义 |

### 组件原则（前端）

- 使用函数组件，不使用类组件
- 单个组件只承担单一职责
- 可复用逻辑必须抽离为自定义 Hook

## 项目状态

→ 当前进度和优先级见 [STATUS.md](STATUS.md)
→ 路线图见 [docs/ROADMAP.md](docs/ROADMAP.md)

## 安全规范

- 永远不信任客户端输入，所有输入必须校验
- 敏感操作必须经过身份与权限校验
- 所有密钥从环境变量读取，禁止硬编码
- 密码等敏感数据必须加密存储
- Token 推荐使用 HttpOnly Cookie

## 禁止事项

- ❌ 不得提交密钥或 API Key 到版本控制
- ❌ 不得使用 `console.log` / `print` 替代日志模块
- ❌ 不得在 api 层直接操作数据库
- ❌ 不得使用 `dangerouslySetInnerHTML`
- ❌ 不得使用裸 `except`（Python）
- ❌ 不得使用拼音命名标识符
