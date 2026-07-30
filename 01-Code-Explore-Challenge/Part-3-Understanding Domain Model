# Part 3 – Understanding Domain Model

## Scenario
To implement new business rules, I first needed to understand the Task Manager's domain model and how the different entities work together.

---

## 1. Extract Domain Model

### Core Entity Classes
The main entities I identified are:
- Task
- TaskStatus
- TaskPriority

### Business Logic Related to Tasks
The application allows users to create, update, complete, and manage tasks. Each task has a status and a priority that determine how it is tracked and displayed.

### Domain Terminology
Important terms used in the application include:
- Task
- Status
- Priority
- Completed
- Pending
- Storage
- Command Line Interface (CLI)

---

## 2. Form Initial Understanding

### Entity Relationship Diagram

```
Task
├── Title
├── Description
├── Status (TaskStatus)
└── Priority (TaskPriority)
```

### Explanation of Each Entity

**Task**
Represents a task created by the user. It stores information such as the title, description, status, and priority.

**TaskStatus**
Represents the current state of a task, such as Pending or Completed.

**TaskPriority**
Represents the importance or urgency of a task, such as Low, Medium, or High.

### Questions or Confusion

- How are task priorities validated?
- Can a completed task be edited?
- Can multiple tasks have the same priority?

---

## 3. Apply the Domain Understanding Prompt

### Prompt Used

Help me understand the domain model of this Task Manager project. Identify the main entities, explain how they relate to each other, describe the business rules, and point out any important concepts I should understand before adding new features.

### Current Understanding

The project is centered around the Task entity. Each task has a status and a priority, and the application manages tasks using the command-line interface while storing data through the storage component.

### Questions for AI

- Which entity is the most important?
- How are task states managed?
- Are there any business rules that prevent invalid task updates?

---

## 4. Test My Knowledge

### Answers to AI Questions

The Task entity is the central object in the application. Status keeps track of task progress, while Priority helps organize tasks according to importance. The storage component saves task data, and the CLI allows users to interact with the application.

### Revised Entity Diagram

```
Task
├── Title
├── Description
├── Status
├── Priority
└── Storage
```

### Glossary

**Task** – A unit of work managed by the application.

**TaskStatus** – The current state of a task.

**TaskPriority** – The importance level of a task.

**CLI** – Command Line Interface used to interact with the application.

**Storage** – The component responsible for saving and loading task data.
