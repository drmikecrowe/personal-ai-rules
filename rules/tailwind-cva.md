# Tailwind CSS - Component Authoring (UI Layer)
- Last Updated: 2025-08-30
- Tags: tailwind css cva
- Version: 1.0


- **Use CVA**: You MUST use `class-variance-authority` (CVA) for all component variants (e.g., intent, size, state). You MUST merge classes with `tailwind-merge`.
- **Expose Layout Needs as Variants**: Instead of hardcoding `w-full`, expose a `fullWidth` boolean variant.
- **No Responsive Classes**: Responsiveness belongs in parent layout containers.
- **Marginless by Default**: Spacing is the responsibility of the parent container, which should use `gap-*` or `space-*`.
- **Accessibility First**: All interactive components MUST include `focus-visible` styles and `disabled:` state variants by default.
