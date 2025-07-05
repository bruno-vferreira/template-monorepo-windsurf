---
description: Initial Setup for Next.js 15+ with App Router, React 19, tailwind and ShadCN
---

## Goal
Guide the automated creation of a Next.js 15+ project using App Router, with TypeScript, ESLint, Prettier, ShadCN, and TailwindCSS setup, plus initial folder structure and useful scripts.

### 1. Create base project
  - use `packages/web` as root directory for the project
  - use turbopack as the default compiler
  - Generate the initial project:
    - [create-next-app](./rules/nextjs/create-next-app.md)

### 2. Install dependencies
  Install dependencies for the project
    - [install-dependencies](./rules/nextjs/install-dependencies.md)

### 3. Configure dependencies
  Configure dependencies for the project
    - [configure-dependencies](./rules/nextjs/configure-dependencies.md)

### 4. Create color palette
  Create if not created previously color palette for the project
    - [style-guide-color-palette](./rules/config/style-guide-color-palette.md)

### 5. Create base components
  Create base components for the project
    - [components](./rules/nextjs/components.md)

### 6. Create Layout
  Create default RootLayout and Layout for the project
    - [layout](./rules/nextjs/layout.md)

### 7. Create base pages
  - create not-found page
  - create defaults pages (index, about, contact)
    - index page
      create landing page example with hero section and a footer
    - about page
      create about page example with a header and a footer
    - contact page
      create contact page example with a header and a footer

### 8. Check Build
  - Build the project and check if it works

### 9. Finally
  - Create a Dockerfile for the project