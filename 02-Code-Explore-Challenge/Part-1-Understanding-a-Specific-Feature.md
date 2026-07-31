# Code Understanding Journal

## Exercise Part 1: Understanding a Specific Feature

### Feature Selected
Task Creation and Status Updates

---

## 1. Files Related to This Feature

The following files work together to implement task creation and status updates:

- app.py
- models.py
- storage.py
- cli.py

---

## 2. Main Components Involved

### app.py
The `TaskManager` class contains the business logic for the application. It creates tasks, updates task status, updates priorities, manages tags, and communicates with the storage layer.

### models.py
This file defines the data structures used by the application:
- Task
- TaskStatus
- TaskPriority

A Task object stores information such as the title, description, priority, due date, status, and tags.

### storage.py
This file is responsible for storing and retrieving tasks. It saves tasks to a JSON file, loads tasks when the application starts, updates existing tasks, deletes tasks, and searches for tasks.

### cli.py
This file provides the command-line interface. It accepts user commands and calls the appropriate methods in the TaskManager class.

---

## 3. Execution Flow

### Task Creation

1. The user enters a command in the CLI.
2. `cli.py` calls `TaskManager.create_task()` in `app.py`.
3. `TaskManager` creates a new `Task` object using `models.py`.
4. The task is sent to `TaskStorage` in `storage.py`.
5. The task is saved to `tasks.json`.

### Status Update

1. The user requests to update a task's status.
2. `cli.py` calls `TaskManager.update_task_status()`.
3. The task is retrieved from storage.
4. The task status is updated.
5. The updated task is saved back to `tasks.json`.

---

## 4. How Data is Stored and Retrieved

The application stores all tasks in a file named `tasks.json`.

The storage layer:
- Loads tasks when the application starts.
- Saves new tasks.
- Updates existing tasks.
- Retrieves tasks when requested.
- Deletes tasks when necessary.

---

## 5. Design Patterns Discovered

### Separation of Responsibilities

Each file has a specific responsibility:

- `cli.py` handles user interaction.
- `app.py` contains the business logic.
- `models.py` defines the data structures.
- `storage.py` manages data storage.

This separation makes the code easier to understand, maintain, and extend.

### Layered Architecture

The application follows a layered architecture:

User
↓
CLI (cli.py)
↓
TaskManager (app.py)
↓
Storage (storage.py)
↓
tasks.json

Each layer has a specific responsibility and communicates with the next layer.

---

## Summary

The task creation and status update feature starts with user input in `cli.py`. The request is processed by the `TaskManager` class in `app.py`, which creates or updates a `Task` object defined in `models.py`. Finally, `storage.py` saves the changes to `tasks.json`. This design keeps the application modular, organized, and easy to maintain.
