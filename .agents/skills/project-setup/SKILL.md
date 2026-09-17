---
name: project-setup
description: >-
  当用户要求初始化项目、搭建新项目、创建项目骨架、安装依赖、配置开发环境、
  或选择技术栈时激活。负责项目脚手架搭建与初始化的完整流程。
---

# 项目初始化

引导完成从技术栈选择到项目可运行的完整初始化流程。

## 步骤

### 1. 确认技术栈

- 读取 `stacks/README.md` 查看所有可用预设
- 可选预设：
  - `react-typescript`：React + TypeScript + Vite
  - `vue-typescript`：Vue 3 + TypeScript + Vite
  - `nextjs`：Next.js（App Router）
  - `python-fastapi`：Python + FastAPI
  - `go-gin`：Go + Gin
- 如果用户未指定，询问用户选择前端和后端技术栈
- 读取对应的 `stacks/<preset>.md` 获取详细配置

### 2. 初始化项目结构

- 按照预设文件中的「推荐目录结构」创建目录
- 创建必要的配置文件（`package.json` / `pyproject.toml` / `go.mod` 等）
- 安装预设中列出的核心依赖

### 3. 配置开发工具

- 确认 `.editorconfig` 已存在
- 配置 Linter（ESLint / Ruff / golangci-lint）
- 配置 Formatter（Prettier / Black / gofmt）
- 配置 TypeScript（如适用）
- 配置测试框架

### 4. 更新项目文档

- 更新 `AGENTS.md` 中的技术栈和关键命令
- 更新 `STATUS.md` 中的当前阶段
- 确认 `DESIGN.md` 的预设风格

### 5. 验证

```bash
# 验证项目能正常启动
pnpm dev          # 前端
# 或
python -m uvicorn app.main:app  # 后端

# 验证测试框架可用
pnpm test         # 前端
# 或
pytest            # 后端

# 验证 lint 通过
pnpm lint         # 前端
```

验证清单：
- [ ] 项目目录结构符合预设规范
- [ ] 所有依赖安装成功
- [ ] 开发服务器能正常启动
- [ ] 测试框架能正常运行
- [ ] Lint 检查通过
