# Personal AI Rules Repository

This repository contains my personal coding rules, standards, and guidelines for use with AI coding assistants through the [agent-rules-mcp](https://github.com/4regab/agent-rules-mcp) server.

## Structure

```
personal-ai-rules/
├── rules/                     # Main rules directory
│   ├── general/              # General coding principles
│   ├── languages/            # Language-specific rules
│   ├── frameworks/           # Framework-specific guidelines
│   ├── architecture/         # Architecture and design patterns
│   ├── security/            # Security best practices
│   ├── testing/             # Testing guidelines
│   └── workflow/            # Development workflow rules
├── templates/               # Code templates and scaffolds
├── examples/               # Example implementations
└── docs/                  # Additional documentation
```

## Usage with MCP

To use these rules with the agent-rules-mcp server, configure your MCP client:

```json
{
  "mcpServers": {
    "personal-rules": {
      "command": "npx",
      "args": ["-y", "agent-rules-mcp@latest"],
      "env": {
        "GITHUB_OWNER": "drmikecrowe",
        "GITHUB_REPO": "personal-ai-rules",
        "GITHUB_PATH": "rules",
        "GITHUB_BRANCH": "main"
      },
      "disabled": false
    }
  }
}
```

## Available Commands

- **List Rules**: `@list_rules` - Shows all available rule domains
- **Get Rules**: `@get_rules domain-name` - Retrieves specific rule content
- **Get Multiple**: `@get_rules domain1,domain2` - Retrieves multiple rules

## Core Principles System

### Always-Apply Rules

Some rules should be applied in every interaction. Start each session with:

```
@get_rules core-principles,code-review-process,problem-solving-heuristics,transparency-standards,ai-collaboration-protocol,silent-execution-protocol,documentation-workflow,testing-principles,clean-code,content-policy
```

### Potential Rules

Special-purpose rules that require explicit activation:

```
@get_rules security-first         # 🔒 OWASP security guidelines
@get_rules tasksync-feedback      # 🔄 Continuous feedback loops
@get_rules performance-optimization # 🐐 Performance optimization best practices
@get_rules security-first,performance-optimization  # Multiple together
```

### Rule Hierarchy

1. **Core Principles** - Always apply (10 fundamental rules)
2. **Potential Rules** - Apply when specific capabilities needed (security-first, tasksync-feedback)
3. **Domain Rules** - Apply based on technology (react-_, typescript-_, etc.)
4. **Project Rules** - Apply for specific project contexts

## Usage Examples

### Standard Development Session

```bash
# Core principles + domain rules
@get_rules core-principles,taskflow-planning,taskflow-feedback
```

### Security-Critical Development

```bash
# Core + security for auth/API work
@get_rules core-principles,security-first,amplify-backend-implementation,typescript-best-practices
```

### Collaborative Development Session

```bash
# Core + continuous feedback for iterative work
@get_rules core-principles,tasksync-feedback,effect-core-principles,react-component-design
```

### Performance-Focused Development

```bash
# Core + performance for optimization work
@get_rules core-principles,performance-optimization,react-performance-optimization,typescript-best-practices
```

### Maximum Coverage Session

```bash
# Everything: core + potential + domain
@get_rules core-principles,security-first,performance-optimization,tasksync-feedback,react-component-design,typescript-best-practices
```

## Contributing to This Repository

When adding new rules:

1. Use descriptive, kebab-case filenames
2. Include metadata in the header
3. Follow the recommended structure
4. Test locally before committing

## Rule Format

Each rule file should follow this structure:

```markdown
# Rule Title

- Last Updated: YYYY-MM-DD
- Description: Brief description of the rules
- Version: X.X

## Overview

Brief overview of what this rule covers.

## Guidelines

Specific guidelines and best practices.

## Examples

Code examples demonstrating the rules.
```

## License

MIT License - Feel free to use and adapt these rules for your own projects.
