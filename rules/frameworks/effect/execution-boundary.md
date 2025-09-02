---
title: Effect Service Pattern - Execution Boundary
last_updated: 2025-08-30
description: Where to execute Effects (`E.runPromise`) - only in XState machine actors.
tags: effect typescript xstate
version: 1.0
---

- **Service Layer Purity**: Functions within the service layer (`src/services/**`) MUST return a composable `Effect`. They describe _what_ to do, but do not execute it.
- **MUST NOT** call `E.runPromise` inside a service.
- **Execution at the Edge**: The execution of an `Effect` (calling `E.runPromise`) MUST only occur at the "edge" of the application. In this project, the **only edge is inside the actors of an XState machine** (`src/machines/**/*.ts`).
- **Rationale**: This enforces a strict separation of concerns, making business logic pure, composable, and testable.
