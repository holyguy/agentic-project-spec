[English](README.md) | [简体中文](README.zh-CN.md)

# 🚀 Agentic Project Template

跨 AI Agent 兼容的项目开发模板。让 Claude Code、Codex、OpenCode、Antigravity、CodeBuddy 等主流 AI Agent 都能无缝接管项目的任何开发阶段。

## 特性

- 📋 **统一 Agent 配置** — 以 AGENTS.md 为核心，兼容所有主流 AI 编码 Agent
- 🎨 **设计体系** — Google Stitch DESIGN.md 格式，多风格预设可选
- 🔧 **项目级 Skills** — 7 个开箱即用的开发技能，可自定义扩展
- 📊 **项目管理** — STATUS.md 实时状态、ADR 架构决策、ROADMAP 路线图
- 🏗️ **技术栈预设** — React / Vue / Next.js / FastAPI / Go 多套预设可选

## 快速开始

### 1. 使用模板

```bash
# 克隆模板
git clone https://github.com/your-org/agentic-project-template.git my-project
cd my-project

# 移除模板的 git 历史
rm -rf .git && git init
```

### 2. 初始化项目

1. 编辑 `AGENTS.md`：填写项目概述和技术栈
2. 选择技术栈预设：参考 `stacks/README.md`
3. 选择设计风格：参考 `.stitch/presets/README.md`，更新 `DESIGN.md`
4. 编辑 `STATUS.md`：设置初始项目状态
5. 编辑 `docs/CONTEXT.md`：定义领域术语

### 3. 开始开发

用任意 AI Agent 打开项目，Agent 会自动读取配置并遵循项目规范。

## 目录结构

```
.
├── AGENTS.md                # 核心规则（所有 Agent 统一入口）
├── CLAUDE.md                # Claude Code 专属指针
├── GEMINI.md                # Antigravity 专属指针
├── CODEBUDDY.md             # CodeBuddy 专属指针
├── DESIGN.md                # 设计体系（Google Stitch 格式）
├── STATUS.md                # 项目实时状态
├── .agents/                 # 统一 Agent 配置目录
│   ├── skills/              # 项目级 Skills（7 个内置）
│   ├── rules/               # 编码规范
│   └── mcp_config.json      # MCP 服务器配置
├── .stitch/presets/          # 设计风格预设
├── stacks/                  # 技术栈预设
├── docs/                    # 项目文档
│   ├── ARCHITECTURE.md      # 架构设计
│   ├── CONTEXT.md           # 领域模型
│   ├── ADR/                 # 架构决策记录
│   ├── ROADMAP.md           # 路线图
│   └── CHANGELOG.md         # 变更日志
├── .claude/skills/          # Claude 技能指针
├── .codebuddy/skills/       # CodeBuddy 技能指针
├── .opencode/commands/      # OpenCode 命令指针
└── src/                     # 源代码（按技术栈初始化）
```

## Agent 兼容性

| Agent | 配置入口 | Skills 发现 | 状态 |
|:------|:---------|:------------|:-----|
| Claude Code | CLAUDE.md → AGENTS.md | .claude/skills/ (指针) | ✅ |
| Codex | AGENTS.md | .agents/skills/ | ✅ |
| OpenCode | AGENTS.md | .opencode/commands/ (指针) | ✅ |
| Antigravity | GEMINI.md + AGENTS.md | .agents/skills/ (原生) | ✅ |
| CodeBuddy | CODEBUDDY.md → AGENTS.md | .codebuddy/skills/ (指针) | ✅ |

## 自定义扩展

### 添加自定义 Skill

在 `.agents/skills/` 下创建新目录，包含 `SKILL.md`：

```markdown
---
name: my-custom-skill
description: >-
  描述何时使用此技能。
---

# 自定义技能名称

## 步骤
1. ...
```

### 添加技术栈预设

在 `stacks/` 下创建新的 `.md` 文件，参考现有预设格式。

### 添加设计风格预设

在 `.stitch/presets/` 下创建新的 `.md` 文件，参考现有预设格式。

## 许可证

MIT
