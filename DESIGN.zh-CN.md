---
version: "1.0"
name: "Project Design System"
description: "项目统一设计体系。生成 UI 前必须读取本文件。"
preset: "minimal-modern"

colors:
  primary: "#2563EB"
  primary-hover: "#1D4ED8"
  secondary: "#6B7280"
  accent: "#F59E0B"
  success: "#10B981"
  warning: "#F59E0B"
  error: "#EF4444"
  info: "#3B82F6"
  background: "#FFFFFF"
  surface: "#F9FAFB"
  text-primary: "#111827"
  text-secondary: "#6B7280"
  border: "#E5E7EB"

typography:
  font-family-display: "Inter"
  font-family-body: "Inter"
  font-family-mono: "JetBrains Mono"
  h1:
    fontSize: "2.25rem"
    fontWeight: "700"
    lineHeight: "2.5rem"
  h2:
    fontSize: "1.5rem"
    fontWeight: "600"
    lineHeight: "2rem"
  h3:
    fontSize: "1.25rem"
    fontWeight: "600"
    lineHeight: "1.75rem"
  body:
    fontSize: "1rem"
    fontWeight: "400"
    lineHeight: "1.5rem"
  small:
    fontSize: "0.875rem"
    fontWeight: "400"
    lineHeight: "1.25rem"

spacing:
  xs: "4px"
  sm: "8px"
  md: "16px"
  lg: "24px"
  xl: "32px"
  2xl: "48px"
  3xl: "64px"

rounded:
  sm: "4px"
  md: "8px"
  lg: "12px"
  xl: "16px"
  full: "9999px"

shadows:
  sm: "0 1px 2px 0 rgba(0, 0, 0, 0.05)"
  md: "0 4px 6px -1px rgba(0, 0, 0, 0.1)"
  lg: "0 10px 15px -3px rgba(0, 0, 0, 0.1)"

breakpoints:
  sm: "640px"
  md: "768px"
  lg: "1024px"
  xl: "1280px"

animation:
  duration-fast: "150ms"
  duration-normal: "300ms"
  duration-slow: "500ms"
  easing: "cubic-bezier(0.4, 0, 0.2, 1)"
---

# 设计哲学

我们的设计体系致力于提供一致、清晰且易用的用户界面。我们遵循“内容优先”的原则，通过留白、清晰的排版和直观的交互来引导用户。

## 风格预设说明

本项目支持多风格切换，相关配置文件请参考 `.stitch/presets/` 目录。
修改 front matter 中的 `preset` 字段，或加载不同的预设文件以应用特定风格。

## 色彩系统使用指南

- **主色 (Primary)**：用于最重要的动作、按钮和交互元素。
- **辅助色 (Secondary)**：用于次要按钮、图标和较弱的提示。
- **语义色 (Success/Warning/Error/Info)**：用于状态反馈、警告提示和系统消息。
- **背景色与表面色 (Background & Surface)**：区分层级，卡片或弹窗使用 Surface，底层使用 Background。
- **文本色 (Text)**：确保良好的对比度。

## 排版系统使用指南

- **标题 (H1-H3)**：用于页面、区块和卡片的标题。遵循层级递进。
- **正文 (Body)**：标准文本内容。
- **小字 (Small)**：用于注释、辅助说明和页脚。

## 间距系统使用指南

统一使用 4px 和 8px 的倍数。
- 元素内边距（如按钮）：使用 `sm` 或 `md`。
- 模块间距：使用 `lg` 或 `xl`。
- 大区块分隔：使用 `2xl` 或 `3xl`。

## 组件设计指南

- **按钮 (Button)**：需要明确的 Hover/Active 态反馈。圆角统一使用 `rounded.md`。
- **卡片 (Card)**：使用 `surface` 背景色，搭配 `shadow.sm`，Hover 时可加深阴影。
- **表单 (Form)**：输入框需要明确的边框 (Border) 和获取焦点时的环绕高亮 (Focus Ring)。
- **导航 (Navigation)**：当前选中项需有明显的视觉区分（如加粗或主色高亮）。
- **模态框 (Modal)**：必须带有半透明遮罩，具备明确的关闭按钮，并支持 ESC 键关闭。

## Do's and Don'ts

- **Do**: 保持界面留白，呼吸感。
- **Do**: 使用明确的文字标签代替含义不清的图标。
- **Do**: 保证所有的点击热区至少为 44x44 px。
- **Don't**: 在同一个页面使用过多的不同字号和颜色。
- **Don't**: 忽略错误状态的明确提示，不能只用颜色区分错误（应附带文字说明或图标）。

## 动效规则

- 界面转场：使用 `duration-normal`。
- 微交互（如 Hover、Click）：使用 `duration-fast`。
- 避免夸张的弹跳效果，坚持使用 `easing` 提供平滑过渡。

## 无障碍要求

- 所有文本和其背景的对比度需满足 WCAG 2.1 AA 标准 (最小 4.5:1)。
- 支持完整的键盘导航。
- 为图像和图标提供 `aria-label` 或 `alt` 属性。

## 响应式设计原则

- **Mobile First**: 默认样式为移动端，通过 `sm`, `md`, `lg` 等断点逐步增强。
- 避免固定宽度，使用百分比或 Flex/Grid 布局。
