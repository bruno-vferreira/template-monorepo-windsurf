---
trigger: manual
glob:
description:
---

### Create base components
  - use shadcn/ui, lucide-react, next-themes and tailwindcss for all components
  - use typescript for all components
  - use forever shadcn/ui components FIRST
  - [base-components](./base-components.md)
  - create components/ui folder
    - LanguageSwitcher: create internationalization switcher component
    - Button: create button component
    - Input: create input component
    - Select: create select component
    - Switch: create switch component
    - and more components as needed
  - create components folder
    - create Header.tsx
      - add language switcher component
      - add theme toggle component
    - create Footer.tsx
    - create ThemeProvider.tsx
      - use for theme provider [theme-provider](./theme-provider.md)

