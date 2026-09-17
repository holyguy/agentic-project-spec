# Next.js (App Router) 技术栈预设

## 核心技术栈
- **框架**: Next.js (使用 App Router 架构)
- **语言**: TypeScript
- **样式**: Tailwind CSS
- **组件库**: React Server Components (RSC) + Client Components
- **状态管理**: React Context / Zustand (仅客户端需要时)
- **数据获取**: Native `fetch` 结合 Next.js 缓存机制
- **部署**: Vercel 或 Docker 容器化

## 推荐目录结构
```text
src/
├── app/               # App Router 路由目录 (包含 page.tsx, layout.tsx 等)
│   ├── api/           # API Routes (Route Handlers)
│   ├── (auth)/        # 路由组 (不影响 URL 结构)
│   └── globals.css    # 全局样式
├── components/        # 全局组件
│   ├── ui/            # 基础 UI 组件
│   └── shared/        # 业务复用组件
├── lib/               # 核心库函数、第三方服务初始化
├── hooks/             # 自定义 Hooks
├── types/             # TS 类型定义
└── utils/             # 工具函数
```

## 注意事项
- 默认所有组件都是 Server Components。
- 需要使用到客户端交互 (onClick, useState, useEffect 等) 的组件，必须在文件顶部加上 `'use client';` 指令。
- 尽量将 Client Components 推向组件树的叶子节点，以最大化服务器渲染的好处。
