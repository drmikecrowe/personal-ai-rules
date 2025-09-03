---
title: XState Usage and Patterns
last_updated: 2025-09-03
description: Guidelines for using XState for state management in the UI.
tags: xstate, state-management, architecture, react
version: 1.0
---

## Core Architecture

- **Primary Pattern**: All UI elements and user interactions MUST be driven by XState state machine actors.
- **Hierarchy**: State logic MUST follow a strict hierarchy: `App Machine` → `Page Machines` → `Entity Machines`.
  - The `App Machine` manages global state and top-level navigation.
  - `Page Machines` manage the state of a specific page or view, following the `Page.tsx`/`page.machine.ts` co-location pattern.
  - `Entity Machines` manage the state of a single data entity, like an expense report. Each entity machine instance is spawned as an actor by its parent page machine.

## Implementation

- **File Location**: State machines should be co-located with the primary component that uses them, following the `Page.tsx`/`page.machine.ts` pattern.
- **Anti-Patterns to Avoid**:
  - Do NOT bypass state machine checks in the UI.
  - Do NOT use manual state checking (`if (report.status === 'APPROVED')`) in components; instead, rely on the state machine's current state (e.g., `actor.getSnapshot().matches('approved')`).

## Action Routing

Actions sent from the UI MUST be routed according to their type:

- **Navigation Actions** (`DOWNLOAD`, `VIEW`, `EDIT`): Route to the `App Machine`.
- **Entity State-Changing Actions** (`SIGN`, `SUBMIT`, `APPROVE`): Route to the specific `Entity Machine` actor.
- **UI State Actions** (`OPEN_DIALOG`, `TABLE_SORT_CHANGED`): Route to the `Page Machine`.

## Permission Guards

- All state transitions that depend on user roles or ownership MUST be protected by a guard.
- **MUST** use the shared guard functions in the page's `guards/` directory to ensure consistent permission logic across the application.

## React State Management

- **Primary**: Use XState actors for complex state management.
- Use `useState` for simple local component state only.
- Use Context API sparingly and only for truly global state.
- Keep state as close to where it's used as possible.
- Avoid prop drilling through proper actor-based state management.
- State machine actors handle business logic; components handle UI state.
