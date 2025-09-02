---
title: Linting and validation
last_updated: 2025-08-30
tags: linting typescript
version: 1.0
---

- **MUST** use `pnpm lint:eslint [path]` in final stages to confirm TypeScript syntax is error-free
- **MUST** use `pnpm lint:tsc` to check types after all edits are complete

- **NOTE**: Formatting is handled automatically (this include import order), focus on syntax and compilation errors only
