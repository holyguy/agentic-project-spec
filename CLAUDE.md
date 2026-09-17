# Claude Code 项目配置

<!-- 本文件是 Claude Code 的专属入口，通用规则统一维护在 AGENTS.md -->

所有通用开发规范见 [AGENTS.md](AGENTS.md)，请先阅读该文件。

## Claude 专属指令

- 优先使用 `.agents/skills/` 中的项目级 Skills
- 生成 UI 组件前先读取 [DESIGN.md](DESIGN.md)
- 技能文件同时存放在 `.claude/skills/` 目录下（指针指向 `.agents/skills/`）
- 使用 `/memory` 记住重要的架构决策
