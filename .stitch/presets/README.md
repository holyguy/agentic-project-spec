# 设计体系风格预设 (Presets)

本项目支持多种设计体系风格。你可以在此目录下找到不同的预设文件。

## 可用预设

1. **[minimal-modern.md](./minimal-modern.md)**
   - 极简现代，低对比度，干练专业。适合文档、博客、工具类应用。
2. **[enterprise.md](./enterprise.md)**
   - 企业级，高数据密度，标准化。适合后台管理、SaaS 平台、数据大屏。
3. **[playful.md](./playful.md)**
   - 活泼有趣，大圆角，明艳色彩。适合面向消费者的应用、教育软件、创意工具。

## 如何切换预设

在根目录的 `DESIGN.md` 文件的 Front Matter 中，修改 `preset` 字段即可切换当前项目的设计风格。例如：

```yaml
---
preset: "playful"
---
```
代码生成器会根据该字段，加载相应的覆盖配置。
