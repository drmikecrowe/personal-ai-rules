---
title: Tailwind CSS - Container Authoring (Layout Layer)
last_updated: 2025-08-30
tags: tailwind css
version: 1.0
---

- **Prefer `gap-*`**: Use `gap-*` for spacing in `flex` or `grid` containers over sibling margins.
- **Centralize Breakpoint Logic**: All responsive prefixes (`sm:`, `md:`, etc.) are applied here.
- **Compose, Don't Override**: Assemble UIs by passing variants to child components. Avoid overriding child styles with utility classes.
