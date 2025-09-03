---
title: Problem-Solving Heuristics
last_updated: 2025-09-03
description: Systematic approaches to debugging, solution finding, and architectural decision-making
tags: problem-solving, debugging, architecture, methodology
version: 1.1
---

## Core Rules

- **Automation**: Ask permission before compiling or starting dev servers.
- **Three Strike Rule**: After 3 failed attempts, question the entire approach.
- **Complexity Threshold**: If a solution requires >20 lines of custom logic in an unfamiliar domain, research established libraries.
- **Proven Patterns First**: Check for existing solutions before writing custom code.
- **Incremental Building**: Start simple and add complexity incrementally.

## Debugging

- **Isolate**: Reproduce consistently, identify minimal case, and eliminate variables.
- **Investigate**: Check recent changes, review logs, and verify dependencies.
- **Validate**: Fix the root cause, test thoroughly, and verify no regressions.
