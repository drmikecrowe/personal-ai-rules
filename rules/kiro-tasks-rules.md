---
title: Kiro Tasks Rules
last_updated: 2025-09-16
description: Workflow for executing tasks in a structured, quality-driven manner
tags: kiro, tasks, workflow, execution, development
version: 1.0
---

## Task Execution Workflow

### Overview

These rules govern how to execute individual tasks from a task list in a structured and quality-driven manner. The focus is on executing one task at a time with careful verification against requirements.

### Task Execution Guidelines

- Look at the task details in the task list
- If the requested task has sub-tasks, always start with the sub tasks
- Only focus on ONE task at a time. Do not implement functionality for other tasks.
- Verify your implementation against any requirements specified in the task or its details.
- Once you complete the requested task, stop and let the user review. DO NOT just proceed to the next task in the list
- If the user doesn't specify which task they want to work on, look at the task list for that spec and make a recommendation on the next task to execute.

Remember, it is VERY IMPORTANT that you only execute one task at a time. Once you finish a task, stop. Don't automatically continue to the next task without the user asking you to do so.

### Task Execution Rules

- Executing tasks without the requirements or design will lead to inaccurate implementations.
- Focus on the specific task at hand and its requirements
- Complete verification of implementation against specifications
- Stop after each task completion for user review

### Task Questions

The user may ask questions about tasks without wanting to execute them. Don't always start executing tasks in cases like this.

For example, the user may want to know what the next task is for a particular feature. In this case, just provide the information and don't start any tasks.

### IMPORTANT EXECUTION INSTRUCTIONS

- You MUST ONLY execute one task at a time. Once it is complete, do not move to the next task automatically.
- You MUST mark completed tasks as [x]
- Always verify implementation against the original requirements and design specifications
- Stop and request user review after completing each individual task

## Usage

- Apply these rules when executing tasks from a task list
- Focus on one task at a time with thorough verification
- Always stop after task completion for user feedback
