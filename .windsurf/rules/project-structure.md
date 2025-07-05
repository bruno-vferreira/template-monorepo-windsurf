---
trigger: manual
glob:
description:
---

### Root Project Structure and Core Directories
  - use the primary root-level directories and the documentation structure:
    - packages/
        - web/
        - api/
        - shared/
        - db/
    - docs/
  - this directory should be a monorepo structure for Frontend and Backend

### Web Package Directory (packages/web)
  - use this directory to store the web application code and dependencies
    - this directory should be a Web Application Frontend and BFF (Backend For Frontend)
    
### API Package Directory (packages/api)
  - use this directory to store the API code and dependencies
    - this directory should be a API Backend
    
### Shared Package Directory (packages/shared)
  - use this directory to store the shared code and dependencies
    - this directory should be a shared code for both Frontend and Backend
    
### DB Package Directory (packages/db)
  - use this directory to store the database schema and migrations


## Do
  - Respecting the root project structure directories

## Don't
  - Never create a new directory in the root level of the project