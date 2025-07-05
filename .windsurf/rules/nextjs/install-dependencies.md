---
trigger: manual
---

### Install dependencies
  - shadcn/ui
    - for install use this command:
      ```bash
        npx shadcn@latest init -b neutral --no-src-dir -y
      ```
    - for add components use this command:
      ```bash
        npx shadcn@latest add <component-name> -y
      ```
  - prettier
  - eslint-config-prettier
  - eslint-plugin-prettier
  - next-intl

### Do
  - Always shadcn/ui First
### Don't
  - Never install radix-ui and your dependencies

