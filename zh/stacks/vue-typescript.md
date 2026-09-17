# Vue 3 + TypeScript 技术栈预设

## 核心技术栈
- **构建工具**: Vite
- **框架**: Vue 3 (Composition API, `<script setup>`)
- **语言**: TypeScript 5+
- **路由**: Vue Router 4
- **状态管理**: Pinia
- **样式**: Tailwind CSS + PostCSS
- **测试**: Vitest + Vue Test Utils

## 推荐目录结构
```text
src/
├── assets/        # 静态资源
├── components/    # 全局组件
├── composables/   # 组合式函数 (Hooks)
├── layouts/       # 布局组件
├── pages/         # 页面视图组件 (可配合 unplugin-vue-router 自动生成)
├── router/        # 路由配置
├── stores/        # Pinia 状态管理
├── styles/        # 全局样式
├── types/         # TS 类型声明
└── utils/         # 工具函数
```

## 关键依赖列表
```json
{
  "dependencies": {
    "vue": "^3.4.0",
    "vue-router": "^4.2.0",
    "pinia": "^2.1.0",
    "@vueuse/core": "^10.7.0"
  },
  "devDependencies": {
    "vite": "^5.1.0",
    "typescript": "^5.3.0",
    "@vitejs/plugin-vue": "^5.0.0",
    "tailwindcss": "^3.4.0",
    "vitest": "^1.3.0",
    "@vue/test-utils": "^2.4.0"
  }
}
```
