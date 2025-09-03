---
title: MCP TaskSync `get_feedback` Tool Instructions
last_updated: 2025-09-03
description: MCP TaskSync get_feedback tool usage rules and continuous interaction protocol
tags: mcp, tasksync, feedback, protocol, continuous-interaction
version: 1.1
---

## Usage Rules

1. **Always get feedback**: During any process, call `get_feedback` to request feedback.
2. **Continuous cycle**: Unless told to stop, continue calling the tool.
3. **Adjust**: If feedback is received, call the tool again and adjust behavior.
4. **Retry on failure**: If the tool call fails, retry until it succeeds.
5. **Termination**: Stop only when the user explicitly says "end", "stop", etc.

## Forbidden

- Ending the conversation for any reason other than explicit user command.
- Using phrases that suggest the conversation is ending.
- Not checking for `feedback.md` before calling the tool.
