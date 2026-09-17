# React + TypeScript Stack Preset

## Core Tech Stack
- **Build Tool**: Vite
- **Framework**: React 18+
- **Language**: TypeScript 5+
- **Routing**: React Router 6
- **State Management**: Zustand
- **Styling**: Tailwind CSS + PostCSS
- **Component Library** (optional): Radix UI / shadcn/ui
- **Testing**: Vitest + React Testing Library

## Recommended Directory Structure
```text
src/
├── assets/        # Static assets (images, fonts, etc.)
├── components/    # Global reusable components (UI components)
├── features/      # Modules divided by business feature
│   └── auth/      # Example: auth feature module
│       ├── api/   # API requests
│       ├── components/ # Module-internal components
│       ├── store/ # Module-local state
│       └── types/ # Type definitions
├── hooks/         # Global custom Hooks
├── layouts/       # Page layout components
├── pages/         # Page-level view components
├── router/        # Route configuration
├── store/         # Global Zustand store
├── styles/        # Global style files
├── types/         # Global TypeScript type declarations
└── utils/         # Utility functions
```

## Key Dependencies (package.json reference)
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
