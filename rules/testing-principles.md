---
title: Testing - Core Principles
last_updated: 2025-08-30
description: Core principles of testing: write testable code, comprehensive tests, no temporary scripts.
tags: testing
version: 1.0
---

## Core Testing Principles

- **Write Testable Code**: Prefer pure functions and use dependency injection.
- **Comprehensive Tests**: Write unit tests for all business logic, especially for state machines and Effect services.
- **Integration Tests**: Use integration tests for UI components to verify actor-based interactions and rendering.

## Testing Standards

### Permanent Tests Only

**In projects with an existing test suite, you MUST create permanent, high-quality unit tests.**

- No temporary or one-off validation scripts that are intended to be deleted
- Extend existing test files for related functionality
- Create new, properly-named test files for new functionality

### Test Quality Requirements

- **Extend and Create**: Add test cases to existing files for related functionality
- **Proper Naming**: Use clear, descriptive test file and test case names
- **Verify Changes**: After making changes, run the test suite to verify nothing has been broken
- **High Quality**: Tests must be maintainable and clearly document expected behavior
