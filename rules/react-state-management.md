# React Component Architecture - State Management (Actor-Based)
- Last Updated: 2025-08-30
- Description: Using XState actors for complex state and `useState` for simple local state.
- Tags: react xstate
- Version: 1.0


- **Primary**: Use XState actors for complex state management
- Use useState for simple local component state only
- Use Context API sparingly and only for truly global state
- Keep state as close to where it's used as possible
- Avoid prop drilling through proper actor-based state management
- State machine actors handle business logic; components handle UI state
