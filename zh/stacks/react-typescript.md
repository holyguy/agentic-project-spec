# React + TypeScript 技术栈预设

## 核心技术栈
- **构建工具**: Vite
- **框架**: React 18+
- **语言**: TypeScript 5+
- **路由**: React Router 6
- **状态管理**: Zustand
- **样式**: Tailwind CSS + PostCSS
- **组件库** (可选): Radix UI / shadcn/ui
- **测试**: Vitest + React Testing Library

## 推荐目录结构
```text
src/
├── assets/        # 静态资源 (图片, 字体等)
├── components/    # 全局复用组件 (UI 组件)
├── features/      # 按业务功能划分的模块
│   └── auth/      # 例如：认证功能模块
│       ├── api/   # 接口请求
│       ├── components/ # 模块内部组件
│       ├── store/ # 模块局部状态
│       └── types/ # 类型定义
├── hooks/         # 全局自定义 Hooks
├── layouts/       # 页面布局组件
├── pages/         # 页面视图级组件
├── router/        # 路由配置
├── store/         # 全局 Zustand store
├── styles/        # 全局样式文件
├── types/         # 全局 TypeScript 类型声明
└── utils/         # 工具函数
```

## 关键依赖列表 (package.json 参考)
```json
{
  "dependencies": {
    "react": "^18.2.0",
    "react-dom": "^18.2.0",
    "react-router-dom": "^6.22.0",
    "zustand": "^4.5.0",
    "clsx": "^2.1.0",
    "tailwind-merge": "^2.2.0",
    "lucide-react": "^0.300.0"
  },
  "devDependencies": {
    "vite": "^5.1.0",
    "typescript": "^5.3.0",
    "tailwindcss": "^3.4.1",
    "postcss": "^8.4.35",
    "autoprefixer": "^10.4.17",
    "vitest": "^1.3.0",
    "@testing-library/react": "^14.2.0"
  }
}
```
