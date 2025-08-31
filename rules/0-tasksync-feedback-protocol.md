# TaskSync Feedback Protocol (POTENTIAL RULE)
- Last Updated: 2025-08-31
- Description: Continuous feedback loop protocol using MCP get_feedback tool for iterative development
- Tags: mcp, feedback, continuous-interaction, tasksync, potential-rule
- Version: 1.0

## Overview

**NOTE: This is a POTENTIAL RULE** - Only apply when using MCP TaskSync tool with `get_feedback` capability.

This protocol enables continuous feedback loops during development tasks, ensuring iterative improvement and user alignment throughout the process.

## Prerequisites

- MCP client with `get_feedback` tool support
- TaskSync MCP server configured
- Project with feedback.md file (or ability to create one)

## Usage Rules

### Mandatory Feedback Loop
1. **During any process, task, or conversation** - call the `get_feedback` tool to request feedback
2. **Continue calling the tool repeatedly** unless termination instructions are explicitly provided
3. **When user feedback is received** - if content is not empty, call tool again and adjust behavior
4. **If tool call fails** - attempt to call again until it succeeds (unless explicit termination given)
5. **Only stop** when user explicitly indicates "end" or "no more interaction needed"

### Feedback Integration
- **Look for feedback.md file first** before using the tool
- **Create feedback.md** if not found
- **Adjust behavior** based on feedback content received
- **Maintain continuity** throughout the development process

## Forbidden Behaviors

**ABSOLUTELY FORBIDDEN:**
- Ending chat/conversation/session for ANY reason except explicit user termination commands ("stop", "end", "terminate", "quit")
- Using phrases that suggest conversation is ending or complete
- Stopping the `get_feedback` cycle under any circumstances
- Acting like the conversation is finished

## Integration with Core Principles

This protocol works alongside your core rules:
- **Silent Execution**: Still work silently, but get feedback after each completion
- **Expert Collaboration**: Use feedback to ensure expert-level alignment
- **Transparency Standards**: Use feedback to clarify assumptions and gaps
- **Code Review Process**: Get feedback on internal review decisions

## Implementation Pattern

```
1. Execute task silently (following silent-execution-protocol)
2. Call get_feedback tool with summary of changes
3. Receive feedback and adjust if needed
4. Repeat until user terminates explicitly
```

## When to Apply This Rule

- **Long development sessions** where iterative feedback is valuable
- **Complex architectural decisions** that benefit from continuous validation
- **Learning new patterns** where feedback helps refine approach
- **Collaborative debugging** sessions

## When NOT to Apply

- **Simple, one-off tasks** where feedback would be excessive
- **Clients without TaskSync MCP support**
- **When user requests completion without iteration**

## Success Criteria

✅ Maintains continuous feedback loop until explicit termination
✅ Integrates feedback into ongoing work seamlessly  
✅ Balances efficiency (silent execution) with collaboration (feedback)
✅ Never assumes tasks are complete without user confirmation
