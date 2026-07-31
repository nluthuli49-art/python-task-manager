## Exercise Part 2: Deepen Understanding Through Guided Questions

### Feature Explored
Task Prioritization System

---

## Initial Understanding

At first, I understood that each task is assigned a priority (such as Low, Medium, or High) when it is created. I believed that the priority was mainly used to label the task and help users identify important tasks.

---

## What I Discovered

After examining the code, I discovered that task priorities are implemented using the `TaskPriority` enum in `models.py`. When a task is created, the priority value provided by the user is converted into a `TaskPriority` object.

The `TaskManager` in `app.py` uses this priority when creating or updating tasks. The `storage.py` file allows tasks to be filtered by priority, making it easy to retrieve only tasks with a specific priority.

---

## Key Insights

- Priorities are defined using an Enum (`TaskPriority`), which limits values to valid options.
- The priority is assigned when creating a task and can also be updated later.
- Tasks can be filtered based on their priority.
- The priority information is stored together with the rest of the task data in `tasks.json`.
- Using Enums helps prevent invalid priority values and makes the code easier to maintain.

---

## Misconceptions That Were Clarified

Initially, I thought the priority automatically changed how tasks were ordered or executed. After reviewing the code, I learned that the priority is mainly used for categorizing and filtering tasks. The code does not automatically sort tasks by priority unless additional logic is implemented.

---

## Summary

The task prioritization system uses the `TaskPriority` enum to ensure valid priority values. The `TaskManager` processes priority changes, while `storage.py` saves and retrieves the information from `tasks.json`. This design improves data consistency and makes task filtering simple and reliable.
