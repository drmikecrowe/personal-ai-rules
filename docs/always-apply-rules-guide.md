# Always-Apply Rules Implementation Guide

This guide explains how to ensure core principles are always applied when using the agent-rules-mcp system.

## Problem Statement

With agent-rules-mcp, rules are retrieved on-demand, but some rules (like code review process, transparency standards) should ALWAYS be applied, regardless of the specific domain or project context.

## Solution: Core Principles System

### 1. Core Principles File

- `rules/core-principles.md` defines which rules are mandatory
- Lists the 6 essential rules that must always be applied
- Provides clear usage instructions for AI assistants

### 2. Implementation Strategies

#### Strategy A: Session Initialization (Recommended)

**At the start of every coding session**, instruct the AI to retrieve core rules:

```
Before we begin, please retrieve and apply the core principles:
@get_rules core-principles,code-review-process,problem-solving-heuristics,transparency-standards,ai-collaboration-protocol,documentation-workflow,testing-principles
```

#### Strategy B: Project-Level Instructions

**In project README or .cursorrules files**, include:

```markdown
## AI Assistant Instructions
Always start by retrieving core principles:
@get_rules core-principles

Then apply relevant domain rules based on the task.
```

#### Strategy C: Custom Prompt Templates

**Create reusable prompts** that include core rule retrieval:

```
# Development Task Template
1. @get_rules core-principles
2. @get_rules {domain-specific-rules}
3. Apply code-review-process to all changes
4. Follow transparency-standards for all communication
```

### 3. Rule Hierarchy

```
├── Core Principles (ALWAYS)
│   ├── code-review-process
│   ├── problem-solving-heuristics  
│   ├── transparency-standards
│   ├── ai-collaboration-protocol
│   ├── documentation-workflow
│   └── testing-principles
├── Domain Rules (CONTEXTUAL)
│   ├── react-*, typescript-*, effect-*
│   └── tailwind-*, amplify-*, xstate-*
└── Project Rules (SPECIFIC)
    └── Project-specific overrides
```

## Usage Examples

### Example 1: React Development Task

```
@get_rules core-principles,react-component-design,typescript-best-practices

Please create a new React component following our standards.
```

### Example 2: Debugging Session

```
@get_rules core-principles,problem-solving-heuristics,debugging-methodology

I'm having an issue with X. Let's troubleshoot this systematically.
```

### Example 3: Architecture Review

```
@get_rules core-principles,architecture-patterns,code-review-process

Please review this architectural approach and provide feedback.
```

## MCP Client Configuration

### Option 1: Multiple MCP Servers

Configure separate MCP servers for core vs. domain rules:

```json
{
  "mcpServers": {
    "core-rules": {
      "command": "npx",
      "args": ["-y", "agent-rules-mcp@latest"],
      "env": {
        "GITHUB_OWNER": "drmikecrowe",
        "GITHUB_REPO": "personal-ai-rules", 
        "GITHUB_PATH": "rules",
        "GITHUB_BRANCH": "main"
      }
    }
  }
}
```

### Option 2: Custom Automation

Create scripts that automatically prepend core rule retrieval to requests.

## Best Practices

1. **Always Start with Core**: Retrieve core-principles at session start
2. **Layer Rules**: Apply core first, then domain-specific
3. **Document Compliance**: Note which rules were applied in solutions
4. **Review Regularly**: Ensure core rules remain current and relevant

## Troubleshooting

### Issue: Rules Not Being Applied Consistently

**Solution**: Use explicit rule retrieval at start of each significant task

### Issue: Too Many Rules to Remember

**Solution**: Use the core-principles.md file as a checklist

### Issue: Conflicts Between Rules

**Solution**: Core principles take precedence, use transparency-standards to document conflicts
