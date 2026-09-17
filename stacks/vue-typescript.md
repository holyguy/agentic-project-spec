# Vue 3 + TypeScript Stack Preset

## Core Tech Stack
- **Build Tool**: Vite
- **Framework**: Vue 3 (Composition API, `<script setup>`)
- **Language**: TypeScript 5+
- **Routing**: Vue Router 4
- **State Management**: Pinia
- **Styling**: Tailwind CSS + PostCSS
- **Testing**: Vitest + Vue Test Utils

## Recommended Directory Structure
```text
src/
├── assets/        # Static assets
├── components/    # Global components
├── composables/   # Composable functions (Hooks)
├── layouts/       # Layout components
├── pages/         # Page view components (can be auto-generated with unplugin-vue-router)
├── router/        # Route configuration
├── stores/        # Pinia state management
├── styles/        # Global styles
├── types/         # TS type declarations
└── utils/         # Utility functions
```

## Key Dependencies
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
