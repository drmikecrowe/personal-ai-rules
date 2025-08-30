# State Machine Patterns (XState) - Core Architecture
- Last Updated: 2025-08-30
- Description: The core architecture of the UI, driven by a hierarchy of XState machines.
- Tags: xstate
- Version: 1.0


- **Primary Pattern**: All UI elements and user interactions MUST be driven by XState state machine actors.
- **Hierarchy**: State logic MUST follow a strict hierarchy: `App Machine` → `Page Machines` → `Entity Machines`.
  - The `App Machine` manages global state and top-level navigation.
  - `Page Machines` manage the state of a specific page or view, following the `Page.tsx`/`page.machine.ts` co-location pattern.
  - `Entity Machines` manage the state of a single data entity, like an expense report. Each entity machine instance is spawned as an actor by its parent page machine.
