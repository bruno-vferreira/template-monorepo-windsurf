---
description: "Generate the complete monorepo structure for your project with all necessary configuration files and dependencies."
model: Claude Sonnet 4
tools: ['changes', 'codebase', 'editFiles', 'extensions', 'fetch', 'findTestFiles', 'githubRepo', 'new', 'openSimpleBrowser', 'problems', 'runCommands', 'runTasks', 'runTests', 'search', 'searchResults', 'terminalLastCommand', 'terminalSelection', 'testFailure', 'usages', 'vscodeAPI', 'microsoft.docs.mcp']
---

# Project Scaffolding Workflow

## Overview

This workflow generates the complete monorepo structure for your project with all necessary configuration files and dependencies.

## Steps

### 1. **Project Structure Guidance & Directory Creation Principle**

- This workflow generates the project's monorepo structure. The generation process **MUST** adhere to the guidelines defined in [project-structure](../instructions/project-structure.instructions.md).
- **Directory Creation Principle:** All specified directories in the subsequent steps will only be created if they do not already exist. The `.github/instructions/` directory itself will not be targeted for creation or modification by this workflow.
- Before proceeding, ensure familiarity with [project-structure](../instructions/project-structure.instructions.md). This document is the source of truth for the overall directory layout, package-specific structures (API, Web, Core, DB), naming conventions, and file organization.
- Confirm the technology stack choices (listed in the "Technology Stack" section above) are compatible with the defined structure, or note any required minor adjustments.

### 2. **Create Web Package Directory (`packages/web`)**

- Create the `packages/web` directory.
- For detailed setup of the Web package, including internal structure, configuration files, UI library initialization (like Shadcn), and essential entry points, refer to the [01-generate-project-nextjs](../../.windsurf/workflows/01-generate-project-nextjs.md) workflow.

### 3. **Create API Package Directory (`packages/api`)**

- Create the `packages/api` directory.

### 4. **Create Core Package Directory (`packages/core`)**

- Create the `packages/core` directory.

### 5. **Create DB Package Directory (`packages/db`)**

- Create the `packages/db` directory.

### 6. **Create docker-compose**

- Create `docker-compose.yml` file from all services

### 7. **Update Readme**

- create or update `README.md` with initial setup instructions

### 8. **Verify Root Project Structure**

- Ensure all root-level directories and files are created correctly.
- Verify that the root `package.json` has correct workspace configurations.
- Detailed verification of individual packages (`web`) should be performed as part of their respective setup workflows.

## Output

- Monorepo structure with all necessary configuration files and dependencies
