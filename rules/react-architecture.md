---
title: React Architectural Patterns
last_updated: 2025-09-03
description: Architectural patterns for React projects using XState and Effect.
tags: react, architecture, xstate, effect
version: 1.1
---

## Actor-Based Rendering (XState)

- UI components MUST NOT contain complex conditional logic for user actions.
- The list of available actions MUST be derived from the state machine actor.
- Use helper functions (e.g., `getReportActionsFromActor()`) to query the actor's state.

## Error Handling (Effect)

- Implement Error Boundaries at appropriate levels.
- Handle async errors using Effect error handling.
- Show user-friendly error messages and fallback UI.
- Use actor error states for business logic errors.

## Data Transformation (Effect)

- Components MUST NOT contain business logic for mapping or transforming data.
- Data transformation should be handled in the `Effect` service layer.

## Testing

- Implement integration tests for complex actor flows.
- Test actor state changes and side effects.
- Use mock data and actor mocks.
