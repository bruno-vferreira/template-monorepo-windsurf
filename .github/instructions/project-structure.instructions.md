---
description: |
  This file provides instructions on the project structure for a monorepo setup.
  It outlines the directories and their purposes, ensuring a clear organization of the codebase.
model: Claude Sonnet 4
applyTo: '**'
---
# Project Structure Rules

## Monorepo Structure

The project follows a monorepo structure with the following packages:

/
├── packages/
│   ├── api/         # Backend API using Hono
│   ├── web/         # Frontend using React
│   ├── core/        # Shared types and utilities
│   └── db/          # Database schema and operations
├── docs/            # Documentation
└── .windsurf/       # Workflows and rules

## Web Package Directory (packages/web)

- use this directory to store the web application code and dependencies
  - this directory should be a Web Application Frontend and BFF (Backend For Frontend)

## API Package Directory (packages/api)

- use this directory to store the API code and dependencies
  - this directory should be a API Backend

## Shared Package Directory (packages/core)

- use this directory to store the shared code and dependencies
  - this directory should be a shared code for both Frontend and Backend

## DB Package Directory (packages/db)

- use this directory to store the database schema and migrations

## **IMPORTANT**

### Do

- Respecting the root project structure directories

### Don't

- Never create a new directory in the root level of the project
