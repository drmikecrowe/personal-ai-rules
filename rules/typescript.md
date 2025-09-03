---
title: TypeScript Best Practices
last_updated: 2025-09-03
description: A summary of best practices for writing TypeScript code.
tags: typescript, best-practices
version: 1.0
---

## Best Practices

- Enable `strict` mode in `tsconfig.json`.
- Use `readonly` for immutable properties.
- Leverage discriminated unions for type safety.
- Use type guards for runtime type checking.
- Implement proper `null` checking.
- Avoid type assertions unless necessary.

## Code Organization

- Keep type definitions close to where they're used.
- Export shared types from dedicated type files (`types` directory).
- Use barrel exports (`index.ts`) for organizing exports.
- Co-locate component props with their components.

## Error Handling

- Create custom error types for domain-specific errors.
- Use `Result` types for operations that can fail.
- Implement proper error boundaries.
- Use `try-catch` blocks with typed `catch` clauses.
- Handle `Promise` rejections properly.

## Functions

- Use explicit return types for public functions.
- Use arrow functions for callbacks and methods.
- Prefer `async/await` over `Promise`s.
- Use function overloads for complex type scenarios.

## Naming Conventions

- `PascalCase` for types and interfaces.
- `camelCase` for variables and functions.
- `UPPER_CASE` for constants.
- Use descriptive names with auxiliary verbs (e.g., `isLoading`, `hasError`).
- Prefix interfaces for React props with `Props` (e.g., `ButtonProps`).

## Patterns

- Use the Builder pattern for complex object creation.
- Implement the Repository pattern for data access.
- Use the Factory pattern for object creation.
- Leverage dependency injection.
- Use the Module pattern for encapsulation.

## Type System

- Prefer `interface`s over `type`s for object definitions.
- Use `type` for unions, intersections, and mapped types.
- Avoid using `any`; prefer `unknown` for unknown types.
- Use strict TypeScript configuration.
- Leverage TypeScript's built-in utility types.
- Use generics for reusable type patterns.
