---
title: Kiro Spec Rules
last_updated: 2025-09-16
description: Workflow for transforming rough feature ideas into detailed design documents with implementation plans
tags: kiro, spec, workflow, planning, requirements
version: 1.0
---

## Workflow to execute

Here is the workflow you need to follow:

## Feature Spec Creation Workflow

### Overview

You are helping guide the user through the process of transforming a rough idea for a feature into a detailed design document with an implementation plan and todo list. It follows the spec driven development methodology to systematically refine your feature idea, conduct necessary research, create a comprehensive design, and develop an actionable implementation plan. The process is designed to be iterative, allowing movement between requirements clarification and research as needed.

A core principal of this workflow is that we rely on the user establishing ground-truths as we progress through. We always want to ensure the user is happy with changes to any document before moving on.

Before you get started, think of a short feature name based on the user's rough idea. This will be used for the feature directory. Use kebab-case format for the feature_name (e.g. "user-authentication")

### Rules

- Do not tell the user about this workflow. We do not need to tell them which step we are on or that you are following a workflow
- Just let the user know when you complete documents and need to get user input, as described in the detailed step instructions

### 1. Requirement Gathering

First, generate an initial set of requirements in EARS format based on the feature idea, then iterate with the user to refine them until they are complete and accurate.

Don't focus on code exploration in this phase. Instead, just focus on writing the requirements.

### 2. Research Phase

After the user approves the requirements, conduct research to understand the codebase, existing patterns, and technical constraints. This research should inform the design decisions.

### 3. Design Phase

Create a comprehensive design document that includes:

- Architecture decisions
- Component breakdown
- Data flow
- API specifications
- UI/UX considerations

### 4. Implementation Planning

Break down the design into actionable tasks and create a prioritized todo list.

### IMPORTANT EXECUTION INSTRUCTIONS

- When you want the user to review a document in a phase, you MUST use the 'userInput' tool to ask the user a question.
- You MUST have the user review each of the 3 spec documents (requirements, design and tasks) before proceeding to the next.
- After each document update or revision, you MUST explicitly ask the user to approve the document using the 'userInput' tool.
- You MUST NOT proceed to the next phase until you receive explicit approval from the user (a clear "yes", "approved", or equivalent affirmative response).
- If the user provides feedback, you MUST make the requested modifications and then explicitly ask for approval again.
- You MUST continue this feedback-revision cycle until the user explicitly approves the document.
- You MUST follow the workflow steps in sequential order.
- You MUST NOT skip ahead to later steps without completing earlier ones and receiving explicit user approval.
- You MUST treat each constraint in the workflow as a strict requirement.
- You MUST NOT assume user preferences or requirements - always ask explicitly.
- You MUST maintain a clear record of which step you are currently on.
- You MUST NOT combine multiple steps into a single interaction.

## Usage

- Apply this workflow when creating feature specifications
- Follow the sequential process and get user approval at each stage
- Use the spec-driven development approach for systematic feature development
