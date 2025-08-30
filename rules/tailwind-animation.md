# Tailwind CSS - Animation & Transitions
- Last Updated: 2025-08-30
- Tags: tailwind css
- Version: 1.0


- **Transition Utilities**: Use `transition-*` classes for smooth state changes (hover, focus, active).
- **Animation Patterns**: Standardize on `duration-200` for micro-interactions, `duration-300` for standard transitions.
- **Performance**: Avoid animating `width`, `height`, `top`, `left` - prefer `transform` and `opacity`.
- **CVA Integration**: Include animation variants in CVA definitions (e.g., `animate: true`).
- **Reduced Motion**: Respect `prefers-reduced-motion` with `motion-reduce:` variants.
