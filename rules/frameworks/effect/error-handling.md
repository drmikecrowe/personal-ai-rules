---
title: Effect Service Pattern - Error Handling
last_updated: 2025-08-30
description: Using custom domain-specific errors and propagating them through the Effect chain.
tags: effect typescript
version: 1.0
---

- **MUST** use custom, domain-specific error types (e.g., `AuthError`) to provide clear context.
- Errors **MUST** be propagated through the `Effect` chain.
