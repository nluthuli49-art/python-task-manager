# Exercise: Code Documentation

## Original Code Chosen

**Function:** `calculate_task_score(task)`

This function calculates a task's priority score based on multiple factors including priority level, due date, task status, tags, and recent updates. The higher the score, the more important the task.

---

## Prompt 1 – Comprehensive Function Documentation

### Function Description

The `calculate_task_score(task)` function calculates an overall importance score for a task. It uses the task's priority, due date, status, tags, and last updated date to determine how important the task is compared to others.

### Parameters

| Parameter | Type | Description |
|----------|------|-------------|
| task | Task | A Task object containing priority, due date, status, tags, and updated_at information. |

### Returns

| Type | Description |
|------|-------------|
| int | Returns the calculated task score. Higher scores indicate higher priority tasks. |

### Possible Errors

- AttributeError if the task object is missing required attributes.
- TypeError if invalid data types are provided.

### Example

```python
score = calculate_task_score(task)
print(score)
```

### Notes

- Higher priority tasks receive higher base scores.
- Overdue tasks receive extra points.
- Completed tasks receive lower scores.
- Tasks tagged "blocker", "critical", or "urgent" receive bonus points.
- Recently updated tasks receive additional points.

---

## Prompt 2 – Intent and Logic Explanation

### Purpose

The function calculates a priority score so tasks can be sorted from the most important to the least important.

### Step-by-Step Logic

1. Assign a base score according to the task priority.
2. Increase the score if the task is overdue or due soon.
3. Reduce the score if the task is completed or under review.
4. Increase the score if the task has important tags such as blocker, critical, or urgent.
5. Add bonus points if the task was updated recently.
6. Return the final score.

### Assumptions

- The task object contains all required fields.
- Due dates are valid.
- Tags are stored in a list.

### Suggested Inline Comments

```python
# Calculate the base priority score

# Increase score based on due date

# Reduce score for completed tasks

# Add bonus for important tags

# Add bonus for recently updated tasks

# Return the final score
```

### Possible Improvements

- Validate input before processing.
- Replace hardcoded numbers with constants.
- Improve error handling.
- Add unit tests.
- Allow configurable scoring rules.

---

## Final Combined Documentation

The `calculate_task_score(task)` function determines how important a task is by calculating a numerical priority score. It combines several factors including priority level, due date, task status, important tags, and recent updates. Higher scores indicate tasks that should be completed first.

This approach makes it easy to sort tasks by importance and helps users focus on the most urgent work. Future improvements could include configurable scoring values, better validation, stronger error handling, and additional automated testing.
