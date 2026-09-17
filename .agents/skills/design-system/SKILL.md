---
name: design-system
description: >-
  当用户要求生成 UI 组件、创建页面、构建界面、前端开发、应用设计体系、
  或任何涉及视觉呈现的代码编写时激活。生成任何 UI/前端代码前必须先
  读取 DESIGN.md 获取设计令牌和约束。
---

# 设计体系应用

在编写任何 UI 或前端代码之前，必须执行本指南确保输出符合项目的统一设计体系。

## 步骤

### 1. 读取设计规范

- 读取项目根目录的 `DESIGN.md`
- 解析 YAML front matter 中的设计令牌：
  - `colors`：色彩体系
  - `typography`：排版体系（字体、字号、字重、行高）
  - `spacing`：间距刻度
  - `rounded`：圆角规范
  - `shadows`：阴影层级
  - `breakpoints`：响应式断点
  - `animation`：动效参数
- 确认当前使用的 `preset` 值

### 2. 检查风格预设

- 读取 `.stitch/presets/` 目录，确认当前预设文件
- 如果预设文件中有覆盖令牌，以预设为准
- 可用预设：`minimal-modern`（极简现代）、`enterprise`（企业级）、`playful`（活泼）

### 3. 检查现有组件体系

- 检查项目中是否已有组件库（如 `src/components/`）
- 检查是否使用了 CSS 框架（Tailwind / CSS Modules / Styled Components）
- 复用已有组件的设计模式，保持一致性

### 4. 生成符合规范的代码

生成 UI 代码时严格遵守以下约束：

- 颜色值**只能**使用 DESIGN.md 中定义的令牌，禁止使用任意十六进制值
- 字号、字重、行高**只能**使用排版体系中的预定义值
- 间距**只能**使用间距刻度中的值（4px 的倍数）
- 圆角**只能**使用 `rounded` 中定义的值
- 阴影**只能**使用 `shadows` 中定义的层级
- 动画时长和缓动函数使用 `animation` 中的值
- 点击热区不小于 44×44px
- 文本与背景对比度满足 WCAG 2.1 AA（至少 4.5:1）

### 5. 验证

- [ ] 所有颜色值来自 DESIGN.md 令牌
- [ ] 排版层级正确（H1 > H2 > H3 > body > small）
- [ ] 间距使用一致且来自刻度表
- [ ] 组件具有 Hover / Active / Focus / Disabled 状态
- [ ] 响应式断点正确处理
- [ ] 键盘导航可用
- [ ] `aria-label` / `alt` 属性已添加
