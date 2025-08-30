# Effect Service Pattern - Error Handling
- Last Updated: 2025-08-30
- Description: Using custom domain-specific errors and propagating them through the Effect chain.
- Tags: effect typescript
- Version: 1.0


- **MUST** use custom, domain-specific error types (e.g., `AuthError`) to provide clear context.
- Errors **MUST** be propagated through the `Effect` chain.
