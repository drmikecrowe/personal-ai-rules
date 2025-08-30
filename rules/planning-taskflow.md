# Use planning
- Last Updated: 2025-08-30
- Description: When you need to plan multiple steps to complete a process or you have any complex dependencies.
- Tags: meta planning
- Version: 1.0


When managing tasks or projects, use the TaskFlow MCP tools to create a structured workflow. Follow these guidelines:

1. PLANNING PHASE:
   - When starting a new project or complex task, use the 'plan_task' tool to break it down into manageable tasks.
   - Include subtasks for complex tasks to make them more manageable.
   - Each task should include the following dependencies:
     - Read `memory-bank/AGENTS.md`
     - Review `memory-bank/project-rules/*`
   - Add project dependencies and notes about user preferences or requirements.
   - Use absolute paths when exporting task plans (e.g., "C:/Users/username/Documents/task-plan.md").

2. EXECUTION PHASE:
   - Always use 'get_next_task' to retrieve the next pending task.
   - If a task has subtasks, complete and mark each subtask as done using 'mark_subtask_done' before marking the main task as done.
   - After completing a task, use 'mark_task_done' and provide detailed completion notes.
   - IMPORTANT: After marking a task as done, wait for user approval before proceeding to the next task.
   - Use 'export_task_status' periodically to save the current state of all tasks for reference.

3. DOCUMENTATION:
   - Add notes using 'add_note' when the user mentions important preferences or requirements.
   - Track dependencies with 'add_dependency' when specific tools or libraries are needed.
   - Update task details as needed using 'update_task' or 'update_subtask'.

4. COMPLETION:
   - After all tasks are completed and approved, inform the user that the project is complete.
   - Offer to export a final status report using 'export_task_status'.

Always maintain a structured approach to task management, and keep the user informed about progress.
