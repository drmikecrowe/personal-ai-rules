---
title: Effect Service Pattern
last_updated: 2025-09-03
description: Core principles and patterns for using the Effect library.
tags: effect, typescript, architecture
version: 1.0
---

## Core Principles

- **Composition over Configuration**: Build complex logic by piping together small, simple, reusable functions.
- **Purity & Single Responsibility**: Each function does one thing and is either a pure data transformation or returns an `Effect`.
- **Descriptive Naming**: Function names must clearly describe their purpose.
- **Readability**: Code should read like a story.

## Composition Style: `pipe` vs `gen`

- **Prefer `pipe()`**: For simple, linear flows, `pipe()` is preferred for its readability and explicit data flow.
- **Use `gen()` for Complex Flows**: For more complex scenarios involving multiple intermediate variables or conditional logic, `gen()` (generators) can be used to avoid deeply nested `E.flatMap` calls and improve readability. Use it judiciously.
- **`E.all` for Concurrency**: Use `E.all` to execute independent effects concurrently.

## Service File Structure

1. **Imports**: Use the project-preferred import style.
2. **Schema Definitions**: Local `effect/Schema` types.
3. **Small, Pure Helper Functions**: Promise wrappers, validators, data transformers, schema decoders.
4. **Composed Business Logic**: Intermediate functions that compose helpers.
5. **Main Exported Function**: The primary entry point, composing all pieces.
6. **Service Object Export**: A simple object exporting the main function(s).

## Imports

- **MUST** use the following import style:

    ```ts
    import type { Effect } from "effect/Effect"
    import { Effect as E } from "effect"
    import { pipe } from "effect"
    ```

- **MUST** use the `E.*` namespace for all Effect functions.

## Schema & Validation

- **MUST** use `effect/Schema` for all data validation and parsing.
- **MUST** prefer an `E.succeed(value).pipe(E.filterOrFail(...))` pipeline for validation.

## Error Handling

- **MUST** use custom, domain-specific error types (e.g., `AuthError`).
- Errors **MUST** be propagated through the `Effect` chain.

## Execution Boundary

- Functions within the service layer (`src/services/**`) **MUST** return a composable `Effect`.
- `E.runPromise` **MUST NOT** be called inside a service.
- Execution (`E.runPromise`) **MUST** only occur at the "edge" of the application, which is inside XState machine actors (`src/machines/**/*.ts`).
