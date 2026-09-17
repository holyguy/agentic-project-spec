# 🚀 Agentic Project Template

A cross-AI-Agent compatible project development template. Lets mainstream AI agents like Claude Code, Codex, OpenCode, Antigravity, and CodeBuddy seamlessly take over any development stage of your project.

## Features

- 📋 **Unified Agent Configuration** — AGENTS.md as the core, compatible with all mainstream AI coding agents
- 🎨 **Design System** — Google Stitch DESIGN.md format with multiple selectable style presets
- 🔧 **Project-level Skills** — 7 ready-to-use development skills, customizable and extensible
- 📊 **Project Management** — STATUS.md real-time status, ADR architecture decisions, ROADMAP roadmap
- 🏗️ **Tech Stack Presets** — Multiple presets for React / Vue / Next.js / FastAPI / Go

## Quick Start

### 1. Use the Template

```bash
# Clone the template
git clone https://github.com/your-org/agentic-project-template.git my-project
cd my-project

# Remove the template's git history
rm -rf .git && git init
```

### 2. Initialize the Project

1. Edit `AGENTS.md`: fill in the project overview and tech stack
2. Choose a tech stack preset: see `stacks/README.md`
3. Choose a design style: see `.stitch/presets/README.md`, then update `DESIGN.md`
4. Edit `STATUS.md`: set the initial project status
5. Edit `docs/CONTEXT.md`: define domain terminology

### 3. Start Developing

Open the project with any AI Agent, and it will automatically read the configuration and follow the project conventions.

## Directory Structure

```
.
├── AGENTS.md                # Core rules (unified entry for all Agents)
├── CLAUDE.md                # Claude Code pointer
├── GEMINI.md                # Antigravity pointer
├── CODEBUDDY.md             # CodeBuddy pointer
├── DESIGN.md                # Design system (Google Stitch format)
├── STATUS.md                # Real-time project status
├── .agents/                 # Unified Agent config directory
│   ├── skills/              # Project-level Skills (7 built-in)
│   ├── rules/               # Coding standards
│   └── mcp_config.json      # MCP server config
├── .stitch/presets/          # Design style presets
├── stacks/                  # Tech stack presets
├── docs/                    # Project documentation
│   ├── ARCHITECTURE.md      # Architecture design
│   ├── CONTEXT.md           # Domain model
│   ├── ADR/                 # Architecture Decision Records
│   ├── ROADMAP.md           # Roadmap
│   └── CHANGELOG.md         # Changelog
├── .claude/skills/          # Claude skill pointers
├── .codebuddy/skills/       # CodeBuddy skill pointers
├── .opencode/commands/      # OpenCode command pointers
└── src/                     # Source code (initialized per tech stack)
```

## Agent Compatibility

| Agent | Config Entry | Skills Discovery | Status |
|:------|:-------------|:-----------------|:-------|
| Claude Code | CLAUDE.md → AGENTS.md | .claude/skills/ (pointer) | ✅ |
| Codex | AGENTS.md | .agents/skills/ | ✅ |
| OpenCode | AGENTS.md | .opencode/commands/ (pointer) | ✅ |
| Antigravity | GEMINI.md + AGENTS.md | .agents/skills/ (native) | ✅ |
| CodeBuddy | CODEBUDDY.md → AGENTS.md | .codebuddy/skills/ (pointer) | ✅ |

## Customization

### Add a Custom Skill

Create a new directory under `.agents/skills/` containing a `SKILL.md`:

```markdown
---
name: my-custom-skill
description: >-
  Describe when to use this skill.
---

# Custom Skill Name

## Steps
1. ...
```

### Add a Tech Stack Preset

Create a new `.md` file under `stacks/`, following the format of existing presets.

### Add a Design Style Preset

Create a new `.md` file under `.stitch/presets/`, following the format of existing presets.

## License

MIT
