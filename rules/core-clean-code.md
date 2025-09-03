---
title: Clean Code Guidelines
last_updated: 2025-09-03
description: Clean code best practices for maintainable, readable, and well-structured code
tags: clean-code, maintainability, readability, best-practices, core-rule
version: 1.1
---

## Core Principles

- **Constants**: Use named constants over magic numbers.
- **Names**: Use meaningful names that reveal purpose.
- **Comments**: Comment the "why", not the "what".
- **Single Responsibility**: Each function does one thing.

## Organization

- **DRY**: Don't Repeat Yourself.
- **Structure**: Keep related code together.
- **Encapsulation**: Hide implementation details.

## Quality

- **Refactor**: Continuously refactor and fix technical debt.
- **Testing**: Write readable tests for bugs and edge cases.
- **Commits**: Write clear, small, focused commits.

## Implementation

- **Formatting**: Respect project's formatting.
- **Naming**: Follow project conventions (default: `camelCase` for functions, `PascalCase` for classes, `UPPER_SNAKE_CASE` for constants).
- **Functions**: Keep them small and with few parameters.
- **Error Handling**: Use exceptions and provide context.
