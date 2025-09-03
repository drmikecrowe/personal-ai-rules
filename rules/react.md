---
title: React Best Practices
last_updated: 2025-09-03
description: A summary of best practices for writing React code.
tags: react, best-practices
version: 1.0
---

## Component Design

- Use functional components over class components.
- Keep components small and focused (single responsibility).
- Extract reusable logic into custom hooks.
- Use composition over inheritance.
- Implement proper prop types with TypeScript.

## Code Organization & File Structure

- Group related components in feature-based directories.
- Use kebab-case for files and PascalCase for components.
- Keep styles close to components (e.g., using CVA patterns).
- Use index files for clean imports.
- Place related hooks, utilities, and types close to components.

## Hooks Usage

- Follow the Rules of Hooks strictly.
- Use custom hooks for reusable logic.
- Keep hooks focused and simple.
- Use appropriate dependency arrays in `useEffect` and implement cleanup when needed.

## Forms

- Use controlled components for form inputs.
- Implement proper form validation.
- Handle form submission states with loading indicators.
- Ensure forms are accessible.

## Performance Optimization

- Implement proper memoization (`useMemo`, `useCallback`).
- Use `React.memo` for expensive components.
- Avoid unnecessary re-renders.
- Implement lazy loading for routes and heavy components.
- Use proper `key` props in lists.

## Accessibility

- Use semantic HTML elements.
- Implement proper ARIA attributes.
- Ensure keyboard navigation and focus management.
- Provide alt text for images.

## Testing

- Write unit tests for components using React Testing Library.
- Test user interactions and state transitions.
- Test error scenarios and edge cases.
