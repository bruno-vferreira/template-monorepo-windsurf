---
applyTo: '**'
---
# Technology Stack Guidelines

## 1. Introduction

This document outlines the official technology stack for the project. Adherence to this stack is crucial for maintaining consistency, ensuring compatibility, streamlining onboarding, and facilitating efficient development and collaboration, especially when leveraging AI-assisted coding tools.

## 2. Core Technology Stack

The following technologies have been selected to build and support our platform:

### 2.1. Frontend (packages/web)

* **Framework/Library:** Next.js 15+, React 19
* **Runtime:** Turbopack
* **Language:** TypeScript (with strict mode)
* **Styling:** Tailwind CSS
* **State Management:** Zustand
* **Routing:** Next.js App Router
* **UI Components:** ShadCN
* **Icons:** Lucide React
* **Theming:** Next.js Theme Provider (with next-themes)
* **Authentication:** NextAuth.js (with next-auth)
* **Image Optimization:** Next.js Image (with next/image)
* **SEO:** Next.js Metadata (with next-seo)

### 2.2. Build, Test & Development Tools

* **Package Manager & Runtime:** pnpm
* **Version Control:** Git (with GitHub)
* **Linting & Formatting:** ESLint, Prettier
* **Testing Frameworks:** Jest

### 2.3. Shared Logic (packages/core)

* **Language:** TypeScript
* **Purpose:** Shared types, utility functions, constants, and core business logic used across `api` and `web` packages.

## 3. Tech Stack

  **Proposal:** The proposal of the components below is to be reused throughout the platform, utilizing the components described in section 2.1. This will help maintain consistency, reduce duplication of code, and facilitate efficient development and collaboration.

### 3.1. Default Components (packages/web/components/ui)

* **Proposal:** Prefered to use shadcn components as much as possible
* **LanguageSwitcher:** Create implementation internationalization switcher component
* **Button:** Create implementation button
* **Input:** Create implementation input
* **Select:** Create implementation select
* **Switch:** Create implementation switch
* **Dropdown:** Create implementation dropdown
* **Modal:** Create implementation modal
* **Toast:** Create implementation toast
* **Alert:** Create implementation alert
* **Notification:** Create implementation notification
* **Tooltip:** Create implementation tooltip
* **Auth:** Create implementation auth
* **And more components as needed**

### 3.2. Default Layout (packages/web/components)

* **Header:** Create implementation header
* **Footer:** Create implementation footer
* **Auth:** Create implementation auth (login, register, forgot password, reset password)
* **ThemeProvider:** Create implementation theme provider [theme-provider](./theme-provider.md)

### 3.3. Default Pages (packages/web/app/[locale])

* **Index:** Create implementation Index
* **About:** Create implementation About
* **Contact:** Create implementation Contact
  
## Do

* Use turbopack as the default compiler
* Use pnpm as the default package manager
* Use shadcn components as much as possible

## Don't

* Don't use webpack
* Don't use radix-ui and radix-ui components
