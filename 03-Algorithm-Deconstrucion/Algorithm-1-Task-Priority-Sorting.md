# Exercise 03: Algorithm Deconstruction Challenge

# Algorithm 1: Task Priority Sorting Algorithm

## Overview

The Task Priority Sorting Algorithm calculates a priority score for each task based on multiple factors instead of using only the priority level. It then sorts the tasks from the highest score to the lowest score so that the most important tasks appear first.

---

## Purpose

The purpose of this algorithm is to help users focus on the most important tasks by considering:

- Task priority
- Due date
- Task status
- Task tags
- Last updated time

This creates a smarter task list than sorting by priority alone.

---

## Step-by-Step Explanation

### Step 1: Assign a Base Priority Score

The algorithm assigns each priority level a numerical weight.

| Priority | Weight | Base Score |
|----------|-------:|-----------:|
| LOW | 1 | 10 |
| MEDIUM | 2 | 20 |
| HIGH | 4 | 40 |
| URGENT | 6 | 60 |

The weight is multiplied by 10 to create the base score.

---

### Step 2: Add Due Date Points

The algorithm checks how close the due date is.

| Due Date | Extra Points |
|----------|-------------:|
| Overdue | +35 |
| Due Today | +20 |
| Due Within 2 Days | +15 |
| Due Within 7 Days | +10 |

Tasks with earlier deadlines receive more points.

---

### Step 3: Reduce the Score for Completed Tasks

Completed or reviewed tasks become less important.

- DONE → -50 points
- REVIEW → -15 points

This keeps completed tasks lower in the priority list.

---

### Step 4: Add Points for Important Tags

If a task contains one of these tags:

- blocker
- critical
- urgent

The algorithm adds **8 points**.

---

### Step 5: Add Points for Recently Updated Tasks

If the task has been updated within the last day, the algorithm adds **5 points**.

---

### Step 6: Calculate the Final Score

After all adjustments, the function returns the final score.

Example:

```text
Urgent Priority = 60
Due Tomorrow = +15
Critical Tag = +8
Recently Updated = +5

Final Score = 88
```

---

### Step 7: Sort the Tasks

The `sort_tasks_by_importance()` function:

1. Calculates a score for every task.
2. Sorts the tasks from the highest score to the lowest score.
3. Returns the sorted task list.

---

### Step 8: Return the Top Priority Tasks

The `get_top_priority_tasks(tasks, limit=5)` function returns only the five highest-priority tasks.

---

## Data Flow Diagram

```text
Task
  │
  ▼
Assign Base Priority Score
  │
  ▼
Check Due Date
  │
  ▼
Check Task Status
  │
  ▼
Check Tags
  │
  ▼
Check Last Updated Time
  │
  ▼
Calculate Final Score
  │
  ▼
Sort Tasks
  │
  ▼
Return Highest Priority Tasks
```

---

## Reflection Questions

### 1. How did the AI's explanation change your understanding of the algorithm?

The AI helped me understand that the algorithm uses a weighted scoring system instead of sorting tasks only by priority. It combines several factors to calculate a final score before sorting the tasks.

### 2. What aspects were still difficult to understand?

At first, it was difficult to understand why different weights were assigned to each factor and how they work together to calculate the final score. Reading the code step by step made it easier to understand.

### 3. How would you explain this algorithm to another junior developer?

I would explain that every task receives a score based on its priority, due date, status, tags, and last updated date. After calculating the score, the tasks are sorted from the highest score to the lowest score so that the most important tasks appear first.

### 4. Did you test this understanding against AI?

Yes. I compared my understanding with the AI's explanation and followed the code step by step using example tasks to verify how the score is calculated.

### 5. How might you improve the algorithm?

Possible improvements include:

- Allow users to customize the scoring weights.
- Include estimated effort or task duration.
- Add support for task dependencies.
- Make the scoring system configurable instead of using fixed values.

---

## Key Learning Points

- Weighted scoring produces better task prioritization than using priority alone.
- Multiple task attributes can influence the final priority.
- Breaking an algorithm into smaller steps makes it easier to understand.
- AI is useful for explaining complex algorithms and improving code comprehension.
