# State Machine Patterns (XState) - Action Routing
- Last Updated: 2025-08-30
- Description: How to route actions to the correct XState machine (App, Page, or Entity).
- Tags: xstate
- Version: 1.0


Actions sent from the UI MUST be routed according to their type:

- **Navigation Actions** (`DOWNLOAD`, `VIEW`, `EDIT`): Route to the `App Machine`.
- **Entity State-Changing Actions** (`SIGN`, `SUBMIT`, `APPROVE`): Route to the specific `Entity Machine` actor.
- **UI State Actions** (`OPEN_DIALOG`, `TABLE_SORT_CHANGED`): Route to the `Page Machine`.
