# Effect Service Pattern - Imports
- Last Updated: 2025-08-30
- Description: The required import style for the Effect library.
- Tags: effect typescript
- Version: 1.0


- **MUST** use the following project-preferred import style:
  ```ts
  import type { Effect } from 'effect/Effect'
  import { Effect as E } from 'effect'
  import { pipe } from 'effect'
  ```
- **MUST** use the `E.*` namespace for all Effect functions (e.g., `E.flatMap`, `E.map`, `E.runPromise`).
- **MUST NOT** import individual functions like `flatMap` directly from `effect`.
