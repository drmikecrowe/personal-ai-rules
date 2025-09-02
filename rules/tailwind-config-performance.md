---
title: Tailwind CSS - Configuration & Performance
last_updated: 2025-08-30
tags: tailwind css
version: 1.0
---

- **Authoritative Config**: `tailwind.config.ts` is the source of truth for all theme extensions (colors, spacing, fonts).
- **Minimize Custom CSS**: Rely on utilities.
- **Ensure Purging**: Production builds MUST be configured to purge all unused CSS classes.
- **Bundle Size Monitoring**: Monitor CSS bundle size and set alerts for significant increases.
- **Code Splitting**: Use CSS code splitting strategies for route-based chunks.
- **Caching Optimization**: Leverage CSS caching with proper cache headers and versioning.
