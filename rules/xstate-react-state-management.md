---
title: React Component Architecture - State Management (Actor-Based)
last_updated: 2025-08-30
description: Using XState actors for complex state and `useState` for simple local state.
tags: react xstate
version: 1.0
---

- **Primary**: Use XState actors for complex state management
- Use useState for simple local component state only
- Use Context API sparingly and only for truly global state
- Keep state as close to where it's used as possible
- Avoid prop drilling through proper actor-based state management
- State machine actors handle business logic; components handle UI state
