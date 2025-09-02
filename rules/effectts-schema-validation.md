---
title: Effect Service Pattern - Schema & Validation
last_updated: 2025-08-30
description: Using `effect/Schema` for data validation and parsing.
tags: effect typescript
version: 1.0
---

- **MUST** use `effect/Schema` for all data validation and parsing, especially at service boundaries (API responses, user input).
- **MUST** prefer an `E.succeed(value).pipe(E.filterOrFail(...), ...)` pipeline for validation, instead of `E.try` or direct `E.fail`.
