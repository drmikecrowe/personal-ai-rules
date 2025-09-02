---
title: State Machine Patterns (XState) - Implementation
last_updated: 2025-08-30
description: Where and how to implement XState machines, and anti-patterns to avoid.
tags: xstate
version: 1.0
---

- **File Location**: State machines should be co-located with the primary component that uses them, following the `Page.tsx`/`page.machine.ts` pattern.
- **Anti-Patterns to Avoid**:
  - Do NOT bypass state machine checks in the UI.
  - Do NOT use manual state checking (`if (report.status === 'APPROVED')`) in components; instead, rely on the state machine's current state (e.g., `actor.getSnapshot().matches('approved')`).
