# Part 4: Practical Application

## Scenario
The team needs to implement a new business rule: Tasks that are overdue for more than 7 days should automatically be marked as abandoned unless they are marked as high priority.

## Planning

### Files I would modify
- models.py – Add the business rule for determining when a task becomes abandoned.
- app.py – Update the application logic to check overdue tasks.
- storage.py – Save the updated task status.
- cli.py – Display the new "Abandoned" status and allow users to view it.

### Changes I would make
- Check each task's due date.
- Compare the due date with today's date.
- If a task is more than 7 days overdue and is not marked as high priority, automatically change its status to "Abandoned."
- Save the updated task information.
- Display the new status when listing tasks.

### Questions I would ask my team
- Should the task be marked abandoned automatically every time the program starts?
- Can users change an abandoned task back to active?
- Should completed tasks be excluded from this rule?
- Should users receive a notification when a task is marked abandoned?

## Reflection

### How did the AI prompts help?
The AI prompts helped me identify where the business logic belongs, understand the project structure, and determine which files would likely need to be updated.

### What am I still unsure about?
I am still unsure where the due date is stored and exactly how task status is updated in the application.

### Next steps
- Read the code in models.py and app.py more carefully.
- Trace how tasks are created, updated, and saved.
- Test the application after implementing the new rule.
- Verify that the feature works correctly with different task priorities and due dates.
