# Clean Code Guidelines
- Last Updated: 2025-08-31
- Description: Clean code best practices for maintainable, readable, and well-structured code
- Tags: clean-code, maintainability, readability, best-practices, core-rule
- Version: 1.0

## Core Clean Code Principles

### Constants Over Magic Numbers
- **Replace hard-coded values** with named constants
- **Use descriptive constant names** that explain the value's purpose  
- **Keep constants** at the top of the file or in a dedicated constants file

### Meaningful Names
- **Variables, functions, and classes** should reveal their purpose
- **Names should explain** why something exists and how it's used
- **Avoid abbreviations** unless they're universally understood

### Smart Comments
- **Don't comment on what** the code does - make the code self-documenting
- **Use comments to explain why** something is done a certain way
- **Document APIs**, complex algorithms, and non-obvious side effects

### Single Responsibility
- **Each function should do exactly one thing**
- **Functions should be small and focused**
- **If a function needs a comment** to explain what it does, it should be split

## Code Organization Principles

### DRY (Don't Repeat Yourself)
- **Extract repeated code** into reusable functions
- **Share common logic** through proper abstraction
- **Maintain single sources of truth**

### Clean Structure
- **Keep related code together**
- **Organize code in a logical hierarchy**
- **Use consistent file and folder naming conventions**

### Encapsulation
- **Hide implementation details**
- **Expose clear interfaces**
- **Move nested conditionals** into well-named functions

## Quality Maintenance

### Code Quality Maintenance
- **Refactor continuously**
- **Fix technical debt early**
- **Leave code cleaner than you found it**

### Testing
- **Write tests before fixing bugs**
- **Keep tests readable and maintainable**
- **Test edge cases and error conditions**

### Version Control
- **Write clear commit messages**
- **Make small, focused commits**
- **Use meaningful branch names**

## Integration with Development Process

This clean code rule enhances all other development rules:
- **Code Review Process**: Apply clean code standards in internal expert consultation
- **Testing Principles**: Ensure tests follow same clean code standards
- **Problem-Solving**: Refactor solutions to be clean and maintainable
- **Transparency Standards**: Use clear naming and structure to make code self-documenting

## Implementation Guidelines

### Naming Conventions
- Use intention-revealing names
- Use pronounceable and searchable names
- Avoid mental mapping and encodings
- Pick one word per concept across the codebase

### Function Design
- Keep functions small (ideally under 20 lines)
- Do one thing well
- Use descriptive names that explain the function's purpose
- Minimize number of parameters

### Class Design
- Follow single responsibility principle
- Keep cohesion high and coupling low
- Use composition over inheritance where appropriate
- Make dependencies explicit

### Error Handling
- Use exceptions rather than return codes where appropriate
- Don't return or pass null
- Provide context with exceptions
- Define exception classes in terms of caller's needs

## Success Criteria

✅ Code is self-documenting with clear, meaningful names
✅ Functions and classes follow single responsibility principle
✅ No magic numbers or repeated code blocks
✅ Clean structure with logical organization
✅ Proper encapsulation with clear interfaces
✅ Continuous refactoring maintains code quality
✅ Tests are readable and maintainable
