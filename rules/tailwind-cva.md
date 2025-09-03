---
title: Tailwind CSS with CVA
last_updated: 2025-09-03
description: Best practices for using class-variance-authority (CVA) with Tailwind CSS.
tags: tailwind, css, cva, components
version: 1.0
---

## Component Authoring with CVA

- **Use CVA**: You MUST use `class-variance-authority` (CVA) for all component variants (e.g., intent, size, state).
- **Merge Classes**: You MUST merge classes with `tailwind-merge`.
- **Layout Variants**: Expose layout needs as variants (e.g., `fullWidth: true`) instead of hardcoding `w-full`.
- **No Responsive Classes**: Responsiveness belongs in parent layout containers.
- **Marginless by Default**: Spacing is the responsibility of the parent container.
- **Accessibility First**: All interactive components MUST include `focus-visible` styles and `disabled:` state variants by default.

## Animation

- Include animation variants in CVA definitions (e.g., `animate: true`).

## Testing

- Test all CVA variants for visual regression.
- Document all CVA variants with usage examples.
