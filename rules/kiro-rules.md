---
title: Kiro Rules
last_updated: 2025-09-16
description: Comprehensive workflow rules for structured AI-assisted development using the Kiro methodology
source: https://forum.cursor.com/t/kiro-workflow-inside-cursor/120364
tags: kiro, workflow, planning, execution, development
version: 1.0
---

## Kiro Workflow Rules (Mandatory)

- **Prompt Optimization**:
  - `@get_rules kiro-prompt-rewriting-rules`: Systematic prompt rewriting for clarity and specificity.
- **Requirements Engineering**:
  - `@get_rules kiro-underspecification-optimizer-rules`: Identify behaviors that would frustrate users.
- **Documentation Access**:
  - `@get_rules kiro-context7-rules`: Guidelines for using Context7 documentation tools.
- **Spec Creation**:
  - `@get_rules kiro-spec-rules`: Feature specification and design workflow.
- **Task Execution**:
  - `@get_rules kiro-tasks-rules`: Structured task implementation and verification.

## Usage

- **AI Assistants**: Apply these rules when using the Kiro workflow methodology.
- **Workflow**: Follow the sequential process from planning through execution.
- **Integration**: Use with other development rules for comprehensive project management.

## Recommended Models

- **Planning**: Grok-4, Gemini-2.5-pro, O3 (for reasoning benchmarks)
- **Task Execution**: Sonnet-4-thinking, Claude-4-thinking (for coding with long context)

## Setup

1. Create `.kiro/specs` directory
2. Create `.cursor/rules/kiro-spec.mdc` with spec workflow rules
3. Create `.cursor/rules/kiro-tasks.mdc` with task execution rules
4. Optional: Add user interaction MCP tool for userInput functionality
5. Optional: Apply prompt optimization rules to refine prompts before use
