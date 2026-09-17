---
version: "1.0"
name: "Project Design System"
description: "Unified project design system. Must be read before generating any UI."
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

# Design Philosophy

Our design system is committed to providing a consistent, clear, and easy-to-use user interface. We follow a "content-first" principle, guiding users through whitespace, clear typography, and intuitive interactions.

## Style Preset Notes

This project supports multiple style switches. See the `.stitch/presets/` directory for related config files. Modify the `preset` field in the front matter, or load a different preset file to apply a specific style.

## Color System Guidelines

- **Primary**: for the most important actions, buttons, and interactive elements.
- **Secondary**: for secondary buttons, icons, and weaker hints.
- **Semantic (Success/Warning/Error/Info)**: for status feedback, warnings, and system messages.
- **Background & Surface**: distinguish hierarchy; use Surface for cards/modals, Background for the base layer.
- **Text**: ensure good contrast.

## Typography Guidelines

- **Headings (H1-H3)**: for page, section, and card titles. Follow hierarchical progression.
- **Body**: standard text content.
- **Small**: for annotations, helper text, and footers.

## Spacing Guidelines

Use multiples of 4px and 8px consistently.
- Element padding (e.g., buttons): use `sm` or `md`.
- Module spacing: use `lg` or `xl`.
- Large section separation: use `2xl` or `3xl`.

## Component Design Guidelines

- **Button**: needs clear Hover/Active feedback. Use `rounded.md` for corners.
- **Card**: use `surface` background with `shadow.sm`; deepen shadow on Hover.
- **Form**: inputs need clear borders and a focus ring on focus.
- **Navigation**: the active item needs clear visual distinction (e.g., bold or primary-color highlight).
- **Modal**: must have a semi-transparent overlay, a clear close button, and support ESC to close.

## Do's and Don'ts

- **Do**: keep whitespace and breathing room.
- **Do**: use clear text labels instead of ambiguous icons.
- **Do**: ensure all clickable hit areas are at least 44x44 px.
- **Don't**: use too many different font sizes and colors on the same page.
- **Don't**: ignore clear error-state feedback; don't distinguish errors by color alone (include text or an icon).

## Motion Rules

- Page transitions: use `duration-normal`.
- Micro-interactions (Hover, Click): use `duration-fast`.
- Avoid exaggerated bounce effects; use `easing` for smooth transitions.

## Accessibility Requirements

- Contrast between all text and its background must meet WCAG 2.1 AA (minimum 4.5:1).
- Support full keyboard navigation.
- Provide `aria-label` or `alt` for images and icons.

## Responsive Design Principles

- **Mobile First**: default styles target mobile, progressively enhanced via `sm`, `md`, `lg` breakpoints.
- Avoid fixed widths; use percentages or Flex/Grid layouts.
