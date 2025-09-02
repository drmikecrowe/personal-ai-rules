# Problem-Solving Heuristics

- Last Updated: 2025-08-30
- Description: Systematic approaches to debugging, solution finding, and architectural decision-making
- Tags: problem-solving, debugging, architecture, methodology
- Version: 1.0

## Core Problem-Solving Rules

### Three Strike Rule

**After 3 failed attempts** at fixing an issue, stop and question the entire architectural approach.

- Don't keep trying the same type of solution
- Step back and evaluate if the problem is being approached correctly
- Consider if the underlying architecture or assumptions are flawed

### Complexity Threshold

**If solution requires >20 lines of custom logic** in unfamiliar domain, stop and recommend researching established libraries/frameworks.

- Complex custom solutions in unfamiliar areas are error-prone
- Existing solutions are usually better tested and documented
- Time spent researching proven solutions pays off in maintenance

### Proven Patterns First

**Always check for established solutions** before writing custom implementations.

- Search for existing libraries, frameworks, or patterns
- Look at how similar problems have been solved in the codebase
- Prefer battle-tested solutions over novel approaches

### Incremental Building

**Start with the simplest working example**, then add complexity.

- Build a minimal viable solution first
- Add features and edge cases incrementally
- Validate each step before adding complexity

## Debugging Methodology

### Problem Isolation

1. **Reproduce the issue consistently**
2. **Identify the minimal case** that triggers the problem
3. **Eliminate variables** systematically
4. **Test assumptions** with minimal examples

### Investigation Process

1. **Check recent changes** that might have introduced the issue
2. **Review logs and error messages** thoroughly
3. **Verify dependencies and versions** are correct
4. **Test in isolation** to rule out environmental factors

### Solution Validation

1. **Fix the root cause**, not just symptoms
2. **Test the fix thoroughly** including edge cases
3. **Verify no regressions** were introduced
4. **Document the solution** for future reference

## Documentation Requirements

For issues surpassing the three strike rule or complexity threshold:

- Create detailed log files in `./ai-debugging-log/{Problem}_{TROUBLESHOOTING/RESEARCH}_LOG.md`
- Document each attempt with clear numbering and results  
- Track what works, what doesn't, and final solutions
- Help avoid repeating failed attempts in the future
