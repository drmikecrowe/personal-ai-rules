---
title: Effect Service Pattern - Composition
last_updated: 2025-08-30
description: Using `pipe` and `E.all` for composing Effect-based logic.
tags: effect typescript
version: 1.0
---

- The main exported function MUST be a `pipe()` chain of composed functions that clearly illustrate the process
- Use `E.all` to execute independent effects concurrently.
