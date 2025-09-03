---
title: Tailwind CSS Best Practices
last_updated: 2025-09-03
description: A summary of best practices for using Tailwind CSS.
tags: tailwind, css, best-practices
version: 1.0
---

## Quick Reference

- **Layout**: Containers only.
- **Styling**: UI components only.
- **Spacing**: No margins in UI components; use `gap-*`/`space-*` in containers.
- **Responsiveness**: Containers only.
- **Animations**: Use `transform`/`opacity`, respect reduced motion.
- **Container Queries**: For component-internal responsive behavior.

## Separation of Concerns

- **Layout Components**: Arrange components using `flex`, `grid`, and `gap`. Handle all responsive logic.
- **UI Components**: Define their own appearance (colors, fonts, etc.). Remain marginless.

## Configuration & Performance

- `tailwind.config.ts` is the source of truth for the theme.
- Minimize custom CSS; rely on utilities.
- Ensure production builds purge all unused CSS.
- Monitor bundle size and use code splitting.

## Containers & Layout

- Prefer `gap-*` for spacing in `flex` or `grid` containers.
- Centralize breakpoint logic (`sm:`, `md:`, etc.) in layout containers.
- Compose UIs by passing variants to child components; don't override styles.

## Responsive & Theming

- All styles should be mobile-first.
- Prefer semantic color tokens from the theme (e.g., `bg-primary`).
- Implement dark mode via the `dark:` class strategy.

## Animation & Transitions

- Use `transition-*` classes for smooth state changes.
- Standardize on `duration-200` for micro-interactions and `duration-300` for standard transitions.
- Avoid animating `width`, `height`, `top`, `left`; prefer `transform` and `opacity`.
- Respect `prefers-reduced-motion` with `motion-reduce:` variants.

## Container Queries

- Use `@container` for component-internal responsive behavior.
- Container queries belong in layout containers, not UI components.
- Provide responsive fallbacks for browsers without container query support.

## Testing

- Test breakpoint behavior in layout containers.
- Verify focus states, contrast ratios, and reduced motion support for accessibility.
- Document custom theme tokens and their semantic meaning.
