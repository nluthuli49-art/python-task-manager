## Exercise Part 4: Reflection and Presentation

### High-Level Overview of the Application Architecture

The Task Manager application follows a layered architecture. Each file has a specific responsibility:

- `cli.py` handles user interaction.
- `app.py` contains the business logic through the `TaskManager` class.
- `models.py` defines the Task model and enums such as `TaskStatus` and `TaskPriority`.
- `storage.py` manages saving and loading tasks from `tasks.json`.

This separation of responsibilities makes the application easier to understand, maintain, and extend.

---

### How the Three Key Features Work

#### 1. Task Creation

The user enters task details through the command-line interface. The request is sent to `TaskManager.create_task()`, which creates a new `Task` object. The task is then saved by `TaskStorage` into `tasks.json`.

#### 2. Task Prioritization

Each task is assigned a priority using the `TaskPriority` enum. The priority can be updated later and is used to filter tasks based on importance. The priority value is stored together with the task information.

#### 3. Task Completion

When a user marks a task as complete, the request goes through the CLI to `TaskManager.update_task_status()`. The task is retrieved, its status is changed to `DONE`, and the updated information is saved back to `tasks.json`.

---

### Interesting Design Pattern

One interesting design pattern is the separation of responsibilities. The application separates the user interface, business logic, data models, and storage into different files. This makes the code organized, reusable, and easier to maintain.

---

### Most Challenging Part

The most challenging part was understanding how information moved between different files. Initially, it was difficult to see how `cli.py`, `app.py`, `models.py`, and `storage.py` worked together. Using the guided prompts helped me follow the execution flow step by step and understand how tasks are created, updated, stored, and retrieved.

---

### Reflection

This exercise improved my understanding of reading an existing codebase instead of writing code from scratch. I learned how to trace program execution, identify the responsibility of each file, understand how data flows through the application, and recognize common software design principles such as layered architecture and separation of responsibilities.
