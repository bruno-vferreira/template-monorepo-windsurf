---
trigger: manual
glob:
description:
---
Use `packages/web` as root directory for the project

## Project Structure Next.js
  - .
    - app/
    - components/
    - hooks/
    - public/
    - providers/
    - utils/
    - lib/
    - types/
    - stores/
    - services/

## Create Next.js project
  
  ```bash
    npx create-next-app@latest . \
    --typescript \
    --eslint \
    --tailwind \
    --app \
    --no-src-dir \
    --turbopack \
    --import-alias "@/*" \
    --use-pnpm \
    --git \
    --force
  ```


  
  
