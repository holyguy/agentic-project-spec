# Next.js (App Router) Stack Preset

## Core Tech Stack
- **Framework**: Next.js (App Router architecture)
- **Language**: TypeScript
- **Styling**: Tailwind CSS
- **Components**: React Server Components (RSC) + Client Components
- **State Management**: React Context / Zustand (only when client-side state is needed)
- **Data Fetching**: Native `fetch` combined with Next.js caching
- **Deployment**: Vercel or Docker containerization

## Recommended Directory Structure
```text
src/
├── app/               # App Router route directory (page.tsx, layout.tsx, etc.)
│   ├── api/           # API Routes (Route Handlers)
│   ├── (auth)/        # Route group (does not affect URL structure)
│   └── globals.css    # Global styles
├── components/        # Global components
│   ├── ui/            # Base UI components
│   └── shared/        # Business-reusable components
├── lib/               # Core library functions, third-party service init
├── hooks/             # Custom Hooks
├── types/             # TS type definitions
└── utils/             # Utility functions
```

## Notes
- By default, all components are Server Components.
- Components that need client-side interaction (onClick, useState, useEffect, etc.) must add the `'use client';` directive at the top of the file.
- Push Client Components down to the leaf nodes of the component tree to maximize server rendering benefits.
