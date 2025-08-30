# Effect Service Pattern - Service File Structure
- Last Updated: 2025-08-30
- Description: The required file structure for Effect-based services.
- Tags: effect typescript
- Version: 1.0


Files MUST be structured in the following order:

1.  **Imports**: Using the convention in rule #3.
2.  **Schema Definitions**: Local `effect/Schema` types for parsing or validation.
3.  **Small, Pure Helper Functions**: The core of the file.
    - **Promise Wrappers**: Isolate third-party async calls (e.g., `fetchAuthenticationSession`).
    - **Validators**: Validate data or state (e.g., `validateSessionTokens`).
    - **Data Transformers**: Pure, synchronous functions that reshape data.
    - **Schema Decoders**: Functions that parse data against an `Effect` Schema.
4.  **Composed Business Logic**: Intermediate functions that compose helpers.
5.  **Main Exported Function**: The primary entry point, composing all pieces in a `pipe` chain.
6.  **Service Object Export**: A simple object exporting the main function(s).
