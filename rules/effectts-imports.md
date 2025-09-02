---
title: Effect Service Pattern - Imports
last_updated: 2025-08-30
description: The required import style for the Effect library.
tags: effect typescript
version: 1.0
---

- **MUST** use the following project-preferred import style:

  ```ts
  import type { Effect } from "effect/Effect"
  import { Effect as E } from "effect"
  import { pipe } from "effect"
  ```

- **MUST** use the `E.*` namespace for all Effect functions (e.g., `E.flatMap`, `E.map`, `E.runPromise`).
- **MUST NOT** import individual functions like `flatMap` directly from `effect`.
