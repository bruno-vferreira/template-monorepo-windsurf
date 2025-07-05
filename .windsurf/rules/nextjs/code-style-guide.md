---
trigger: model_decision
description: Code Style & Project structure for Next.js projects
---
## Architecture

### Project Structure
```
/
├── .github/               # GitHub workflows and templates
├── public/                # Static files
├── app/                   # App Router
│   ├── [locale]/          # Locale routes group
│   │   ├── (auth)/        # Auth routes group
│   │   ├── (main)/        # Main app routes group
│   │   └── (shared)/      # Shared routes group
│   ├── api/               # API routes (server actions)
│   ├── favicon.ico
│   ├── globals.css
│   └── layout.tsx
├── components/            # Shared components
│   ├── ui/                # Shadcn UI components
│   ├── forms/             # Form components
│   └── layout/            # Layout components
├── config/                # App configuration
├── hooks/                 # Custom React hooks
├── lib/                   # Utility functions
├── providers/             # Context providers
├── services/              # API services
├── stores/                # State management
├── styles/                # Global styles
├── types/                 # TypeScript types
├── tests/                 # Test files
├── .env.local             # Environment variables
├── next.config.js         # Next.js config
├── package.json
└── tsconfig.json
```

## Naming Conventions

### Files & Directories

- Use `kebab-case` for file and directory names
- Use `PascalCase` for React component file names (e.g., `UserCard.tsx`)
- Use `camelCase` for utility files and hooks (e.g., `useAuth.ts`)

### Components

- Use `PascalCase` for component names
- One component per file
- Use named exports for components

### Variables & Functions

- Use `camelCase` for variables and functions
- Use `UPPER_CASE` for constants
- Prefix boolean variables with `is`, `has`, `should` (e.g., `isLoading`, `hasError`)
- Prefix event handlers with `handle` (e.g., `handleSubmit`)

### Types & Interfaces

- Use `PascalCase` for type and interface names
- Prefix interfaces with `I` (e.g., `IUser`)
- Use type aliases for complex types