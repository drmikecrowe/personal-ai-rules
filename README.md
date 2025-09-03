# Personal AI Rules Repository

This repository contains my personal coding rules, standards, and guidelines for use with AI coding assistants through the [agent-rules-mcp](httpss://github.com/4regab/agent-rules-mcp) server.

## Structure

```
personal-ai-rules/
├── rules/
│   ├── core-rules.md
│   ├── core-ai-collaboration-protocol.md
│   ├── ... (other core rules)
│   ├── amplify.md
│   ├── effect.md
│   ├── performance.md
│   ├── react.md
│   ├── react-architecture.md
│   ├── react-cva.md
│   ├── tailwind.md
│   ├── tailwind-cva.md
│   ├── typescript.md
│   ├── workflow-api-documentation.md
│   ├── ... (other workflow rules)
│   └── xstate.md
├── docs/
└── ...
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

## Rule System

This repository is organized into a `core` set of rules and several domains for different technologies and workflows.

### Core Rules

The `core-rules.md` file defines the set of rules that should be applied in every interaction. These are the fundamental principles for working on any project.

To get all core rules, you can use:

```
@get_rules core-rules
```

This will fetch all the rules referenced in `core-rules.md`.

### Domain Rules

The repository also contains several domain-specific rules for different technologies and workflows. These can be fetched on demand.

- **`amplify`**: AWS Amplify Gen 2 backend rules.
- **`effect`**: Effect-TS service pattern.
- **`performance`**: Performance optimization best practices.
- **`react`**: General React best practices.
- **`react-architecture`**: Architectural patterns for React projects using XState and Effect.
- **`react-cva`**: Patterns for creating component APIs with CVA in React projects.
- **`tailwind`**: Tailwind CSS best practices.
- **`tailwind-cva`**: Best practices for using CVA with Tailwind CSS.
- **`typescript`**: TypeScript best practices.
- **`workflow`**: Various workflow rules (api-documentation, search-tools, etc.).
- **`xstate`**: XState usage and patterns.

## Usage Examples

### Standard Frontend Development

For a standard frontend development session using React, TypeScript, and Tailwind CSS:

```
@get_rules core-rules,react,typescript,tailwind
```

### Frontend Development with CVA

If the project uses CVA for component variants:

```
@get_rules core-rules,react,typescript,tailwind,tailwind-cva,react-cva
```

### Full-Stack Development with Amplify and Effect

For a full-stack development session with Amplify, Effect, React, and TypeScript:

```
@get_rules core-rules,amplify,effect,react,react-architecture,typescript,tailwind
```

### Performance Optimization

When focusing on performance optimization:

```
@get_rules core-rules,performance,react,typescript
```

## Contributing to This Repository

When adding new rules:

1. Use descriptive, kebab-case filenames.
2. Include metadata in the header.
3. Follow the recommended structure.
4. Test locally before committing.

## Rule Format

Each rule file should follow this structure:

```markdown
---
title: Rule Title
last_updated: YYYY-MM-DD
description: Brief description of the rules
tags: tag1, tag2
version: X.X
---

## Section Title

-   Rule content...
```

## License

MIT License - Feel free to use and adapt these rules for your own projects.
