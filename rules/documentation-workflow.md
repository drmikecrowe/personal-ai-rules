---
title: Documentation Workflow
last_updated: 2025-08-30
description: Proactive knowledge capture practices for troubleshooting, lessons learned, and complex debugging
tags: documentation, knowledge-capture, troubleshooting, lessons-learned
version: 1.0
---

## Proactive Documentation Standards

### Memory Bank Authority

- **Memory Bank is Authoritative**: The `memory-bank/` is the single source of truth. ALWAYS consult it before significant work.
- **Priority of Information**: `Memory Bank` > `Codebase` > `Conversation History` > `External Knowledge`
- **Verify Context**: Before starting, check for existing documentation, architecture diagrams, and technology versions.

### Post-Resolution Documentation

#### After Resolving Errors

**Proactively offer** to help draft an entry for the `troubleshooting_log.md`:

- Document the error symptoms and root cause
- Record the solution and verification steps
- Note any patterns or recurring issues
- Include prevention strategies for the future

#### After Complex Tasks

**Proactively offer** to capture key insights in `lessons_learned.md`:

- Document architectural decisions and reasoning
- Record patterns that emerged during implementation
- Note tools, techniques, or approaches that worked well
- Identify areas for future improvement or optimization

## Complex Debugging Documentation

For issues surpassing the three strike rule or complexity threshold:

### Create Detailed Log Files

Location: `./ai-debugging-log/{Problem}_{TROUBLESHOOTING/RESEARCH}_LOG.md`

### Log Structure

```markdown
# {Problem} Troubleshooting Log

- Date: YYYY-MM-DD
- Issue: Brief description of the problem
- Context: Relevant background information

## Attempts

1. **Attempt 1**: Description of approach and result
2. **Attempt 2**: Description of approach and result
3. **Attempt 3**: Description of approach and result

## Solution

- Final approach that worked
- Key insights discovered
- Verification steps taken

## Prevention

- How to avoid this issue in the future
- Warning signs to watch for
```

## Knowledge Capture Standards

### Real-Time Documentation

- **Document decisions** as they're made, not after completion
- **Record reasoning** for non-obvious choices
- **Note alternatives** considered and why they were rejected
- **Track dependencies** and assumptions

### Architecture Documentation

- **Update diagrams** when architectural changes are made
- **Document patterns** that emerge during development
- **Record constraints** and their rationale
- **Maintain technology version records**

### Process Documentation

- **Document workflows** that prove effective
- **Record tool configurations** and setup procedures
- **Note debugging techniques** that work well
- **Capture team decisions** and their context

## Documentation Quality Standards

- **Be Specific**: Include concrete examples and code snippets
- **Be Concise**: Focus on essential information and decisions
- **Be Searchable**: Use clear headings and consistent terminology
- **Be Timely**: Document while context is fresh in memory
