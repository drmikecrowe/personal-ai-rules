---
title: Use planning
last_updated: 2025-09-03
description: When you need to plan multiple steps to complete a process or you have any complex dependencies.
tags: meta planning
version: 1.1
---

## Workflow

1. **Planning**:
    - Use `plan_task` to break down complex tasks.
    - Include subtasks and dependencies (`AGENTS.md`, `project-rules/*`).
2. **Execution**:
    - Use `get_next_task` to get the next task.
    - Mark subtasks and tasks as done (`mark_subtask_done`, `mark_task_done`).
    - **IMPORTANT**: Wait for user approval after each task.
3. **Documentation**:
    - Use `add_note` for user preferences.
    - Use `add_dependency` for tools/libraries.
4. **Completion**:
    - Inform the user when the project is complete.
    - Offer to export a final status report.
