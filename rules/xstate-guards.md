# State Machine Patterns (XState) - Permission Guards
- Last Updated: 2025-08-30
- Description: Using guards to protect state transitions based on user permissions.
- Tags: xstate
- Version: 1.0


- All state transitions that depend on user roles or ownership MUST be protected by a guard.
- **MUST** use the shared guard functions in the page's `guards/` directory to ensure consistent permission logic across the application.
