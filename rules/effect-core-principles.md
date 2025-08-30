# Effect Service Pattern - Core Principles
- Last Updated: 2025-08-30
- Description: Core principles of using the Effect library: composition, purity, naming, and readability.
- Tags: effect typescript
- Version: 1.0


This project has adopted the `Effect` library as the standard for all business logic, data transformations, and asynchronous operations. All new and refactored code MUST follow these patterns.

**Best-in-Class Example:** `/src/services/AmplifyService/auth/fetch-user.ts`

- **Composition over Configuration**: Build complex logic by piping together small, simple, reusable functions.
- **Purity & Single Responsibility**: Each function does one thing. Functions are either pure data transformations or return an `Effect` describing an operation.
- **Descriptive Naming**: Function names must clearly describe their single purpose.
- **Readability**: Code should read like a story. The main exported function's `pipe` chain should clearly describe the business process.
