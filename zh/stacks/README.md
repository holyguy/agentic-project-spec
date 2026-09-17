# 技术栈预设 (Stacks)

本项目提供多种前后端技术栈的初始化预设。选择合适的技术栈预设，可以快速搭建符合最佳实践的项目结构和依赖体系。

## 前端技术栈

1. **[React + TypeScript](./react-typescript.md)**
   - 使用 Vite 构建的客户端渲染 (CSR) 架构。适合复杂的单页应用 (SPA)。
2. **[Vue 3 + TypeScript](./vue-typescript.md)**
   - 使用 Vite 构建的 Vue 生态系统。适合喜欢 Composition API 和灵活响应式系统的团队。
3. **[Next.js (App Router)](./nextjs.md)**
   - 基于 React 的全栈框架。提供服务端渲染 (SSR) 和静态生成 (SSG)，适合需要优秀 SEO 和首屏加载性能的应用。

## 后端技术栈

4. **[Python + FastAPI](./python-fastapi.md)**
   - 现代、快速（高性能）的 Python Web 框架。非常适合构建 RESTful APIs，内置自动验证和交互式文档支持。
5. **[Go + Gin](./go-gin.md)**
   - 极简、高性能的 Go Web 框架。适合构建高并发微服务和核心后端系统。

## 如何使用

在开始生成项目代码时，指定你需要的技术栈（例如，"请使用 Next.js 和 Python FastAPI 预设"）。生成器会自动读取相应的 Markdown 文件，按照约定的目录结构和依赖进行代码生成。
