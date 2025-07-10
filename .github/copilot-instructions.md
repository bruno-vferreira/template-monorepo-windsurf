# Copilot Instructions

## Project Overview

This is a **monorepo template** for creating modern web applications with a structured frontend/backend separation. The template enforces a specific monorepo architecture using pnpm workspaces and includes comprehensive rules for Next.js 15+ development with React 19.

## Architecture & Structure

### Monorepo Layout

The project **MUST** follow this exact structure:

```
/
├── packages/
│   ├── web/         # Next.js 15+ frontend (React 19, TypeScript)
│   ├── api/         # Backend API using Hono
│   ├── core/        # Shared types and utilities
│   └── db/          # Database schema and operations
├── docs/            # Documentation
└── .windsurf/       # AI coding workflows and rules
```

**CRITICAL**: Never create directories at root level outside this structure. All application code goes within `packages/`.

### Web Package Structure (`packages/web/`)

Follow Next.js App Router conventions:

```
packages/web/
├── app/
│   ├── [locale]/          # i18n routing (en, pt-br, es)
│   │   ├── (auth)/        # Auth routes group
│   │   ├── (main)/        # Main app routes group
│   │   └── (shared)/      # Shared routes group
│   ├── api/               # API routes
│   └── layout.tsx         # Root layout
├── components/
│   ├── ui/                # ShadCN components only
│   ├── forms/             # Form components
│   └── layout/            # Layout components
├── i18n/                  # next-intl configuration
├── hooks/                 # Custom React hooks
└── [lib/, stores/, services/, etc.]
```

## Technology Stack

### Frontend (packages/web)

- **Framework**: Next.js 15+ with App Router, React 19
- **Language**: TypeScript (strict mode)
- **Styling**: Tailwind CSS
- **UI Library**: ShadCN/ui components ONLY (never Radix UI directly)
- **State**: Zustand
- **Build**: Turbopack (never webpack)
- **Package Manager**: pnpm (never npm/yarn)
- **Internationalization**: next-intl with `[locale]` routing
- **Theme**: next-themes with custom CSS variables

### Key Configuration

- **Compiler**: Always use Turbopack (`next dev --turbo`)
- **Routing**: App Router with locale-based routing (`/en/`, `/pt-br/`, `/es/`)
- **Components**: Install ShadCN components via `npx shadcn@latest add <component>`

## Development Workflows

### Component Creation

```bash
# Add ShadCN components
npx shadcn@latest add button input select

# Follow naming conventions
# - PascalCase for components: UserCard.tsx
# - camelCase for utilities: useAuth.ts
# - kebab-case for directories: user-profile/
```

### Internationalization Setup

- Configure routing in `i18n/routing.ts` with supported locales
- Create message files: `messages/en.json`, `messages/pt-br.json`, `messages/es.json`
- Use `NextIntlClientProvider` in layouts for client components
- Call `setRequestLocale()` in pages for static rendering

### Project Scaffolding

The project includes automated workflows in `.windsurf/workflows/`:

1. **00-generate-project-scaffold.md**: Creates monorepo structure
2. **01-generate-project-nextjs.md**: Sets up Next.js with full configuration

## Critical Patterns

### Color System

Use the predefined HSL color palette in `globals.css`:

- Primary: `hsl(var(--primary))` (green-based theme)
- Supports light/dark modes with CSS custom properties
- Never hardcode colors - always use design tokens

### State Management

- Local state: React hooks (`useState`, `useReducer`)
- Global state: Zustand stores in `stores/`
- Server state: Next.js Server Components + Server Actions

### File Organization

- **Components**: Feature-based organization in `components/`
- **Types**: Shared types in `packages/core/` for cross-package use
- **Utils**: Package-specific utilities in respective `lib/` directories

## Code Style Conventions

### TypeScript

- Strict mode enabled
- Explicit prop types for components
- Interfaces prefixed with `I` (e.g., `IUser`)
- Boolean variables: `is*`, `has*`, `should*` prefixes
- Event handlers: `handle*` prefix

### Component Patterns

- Default to Server Components
- Use `"use client"` only for interactive elements
- Named exports for components
- One component per file

## Integration Points

### Package Dependencies

- `packages/core`: Shared types and utilities
- `packages/web`: Consumes core types for UI logic
- `packages/api`: Uses core types for API contracts
- `packages/db`: Database schemas shared via core

### Build & Development

- Root `package.json` configures workspace dependencies
- Individual packages have their own `package.json`
- Use pnpm workspace commands: `pnpm --filter web dev`

---

_This template emphasizes consistency, type safety, and modern React patterns. Follow the established conventions and leverage the automated workflows in `.windsurf/` for rapid development._
