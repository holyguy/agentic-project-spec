# Tech Stack Presets (Stacks)

This project provides initialization presets for various frontend and backend tech stacks. Choosing the right preset lets you quickly scaffold a project structure and dependency set that follows best practices.

## Frontend Stacks

1. **[React + TypeScript](./react-typescript.md)**
   - Client-side rendering (CSR) built with Vite. Suitable for complex single-page applications (SPAs).
2. **[Vue 3 + TypeScript](./vue-typescript.md)**
   - The Vue ecosystem built with Vite. Suitable for teams that prefer the Composition API and a flexible reactivity system.
3. **[Next.js (App Router)](./nextjs.md)**
   - A React-based full-stack framework. Provides server-side rendering (SSR) and static site generation (SSG), suitable for apps that need good SEO and fast first-paint performance.

## Backend Stacks

4. **[Python + FastAPI](./python-fastapi.md)**
   - A modern, fast (high-performance) Python web framework. Great for building RESTful APIs, with built-in validation and interactive docs.
5. **[Go + Gin](./go-gin.md)**
   - A minimal, high-performance Go web framework. Suitable for building high-concurrency microservices and core backend systems.

## How to Use

When starting to generate project code, specify the tech stack you need (e.g., "please use the Next.js and Python FastAPI presets"). The generator will automatically read the corresponding Markdown file and generate code following the agreed directory structure and dependencies.
