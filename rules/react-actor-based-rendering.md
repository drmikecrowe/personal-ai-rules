---
title: React Component Architecture - Actor-Based Actions and Rendering
last_updated: 2025-08-30
description: Deriving available user actions from XState actors, not component logic.
tags: react xstate
version: 1.0
---

- UI components MUST NOT contain complex conditional logic to determine available user actions.
- The list of available actions for an entity (e.g., an expense report) MUST be derived from its state machine actor.
- **MUST** use helper functions like `getReportActionsFromActor()` to query the actor's state and permissions to determine which actions are currently possible.
