## Exercise Part 3: Mapping Data Flow

### Feature Explored
Task Completion Data Flow

---

## Data Flow Diagram

User
↓
CLI (cli.py)
↓
TaskManager.update_task_status() (app.py)
↓
Retrieve Task from TaskStorage (storage.py)
↓
Task.mark_as_done() (models.py)
↓
Update task status to DONE
↓
Save updated task to tasks.json
↓
Return success message to the user

---

## State Changes During Task Completion

When a task is marked as complete, the following changes occur:

1. The user selects a task to complete.
2. `cli.py` sends the request to `TaskManager.update_task_status()`.
3. The task is retrieved from storage.
4. The task's status changes from its current state (such as TODO or IN_PROGRESS) to `DONE`.
5. The completion time is recorded (if supported by the Task model).
6. The updated task is saved to `tasks.json`.
7. The application confirms that the task was successfully updated.

---

## Potential Points of Failure

Some possible problems during this process include:

- The task ID does not exist.
- An invalid status value is provided.
- The `tasks.json` file cannot be accessed or saved.
- The task cannot be retrieved from storage.
- Unexpected errors occur while updating or saving the task.

---

## How the Application Persists Changes

The application uses `storage.py` to save all task information in `tasks.json`.

Whenever a task is updated:

- The task object is modified.
- The storage layer saves the updated list of tasks.
- The changes remain available the next time the application is opened.

---

## Summary

The task completion process begins with user input through the CLI. The request is handled by the `TaskManager`, which retrieves the task from storage, updates its status to `DONE`, and saves the changes back to `tasks.json`. This layered design separates user interaction, business logic, data models, and storage, making the application easier to understand and maintain.
