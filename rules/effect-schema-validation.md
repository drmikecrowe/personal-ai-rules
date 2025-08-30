# Effect Service Pattern - Schema & Validation
- Last Updated: 2025-08-30
- Description: Using `effect/Schema` for data validation and parsing.
- Tags: effect typescript
- Version: 1.0


- **MUST** use `effect/Schema` for all data validation and parsing, especially at service boundaries (API responses, user input).
- **MUST** prefer an `E.succeed(value).pipe(E.filterOrFail(...), ...)` pipeline for validation, instead of `E.try` or direct `E.fail`.
