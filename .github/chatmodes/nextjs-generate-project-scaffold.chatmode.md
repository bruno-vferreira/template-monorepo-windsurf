---
description: Generate Next.js project scaffold with monorepo structure.
model: Claude Sonnet 4
applyTo: '**'
tools: ['changes', 'codebase', 'editFiles', 'extensions', 'fetch', 'findTestFiles', 'githubRepo', 'new', 'openSimpleBrowser', 'problems', 'runCommands', 'runTasks', 'runTests', 'search', 'searchResults', 'terminalLastCommand', 'terminalSelection', 'testFailure', 'usages', 'vscodeAPI', 'microsoft.docs.mcp']
---

# Next.js Project Scaffolding Workflow

## Overview

This workflow generates the complete Next.js structure for your project with all necessary configuration files and dependencies.

## Steps

**Use `packages/web` as root directory for the project Next.js**
**Follow the steps below to generate a Next.js project**
**You must follow step by step, without skipping steps.**

### 1. Create base project

- Use turbopack as the default compiler
- Generate the structure project:
  - [create-next-app](./../instructions/nextjs/create-next-app.instructions.md)

### 2. Install dependencies

- Install dependencies for the project
  - [install-dependencies](./../instructions/nextjs/install-dependencies.md)

### 3. Configure dependencies

- Configure dependencies for the project
  - [configure-dependencies](./../instructions/nextjs/configure-dependencies.md)

### 4. Create color palette

- Create if not created previously color palette for the project
  - [style-guide-color-palette](./../instructions/config/style-guide-color-palette.md)

### 5. Create components

- Create base components for the project
  - [tech-stack](./../instructions/nextjs/tech-stack.md)

### 6. Create Layout

- Create default RootLayout and Layout for the project
  - [layout](./../instructions/nextjs/layout.md)

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

## Goal

Guide the automated creation of a Next.js 15+ project using App Router, with TypeScript, ESLint, Prettier, ShadCN, and TailwindCSS setup, plus initial folder structure and useful scripts.
