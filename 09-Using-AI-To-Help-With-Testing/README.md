# Exercise: Using AI to Help with Testing

## Part 1: Understanding What to Test

### Exercise 1.1: Behavior Analysis

### Behaviors Identified

The `calculateTaskScore()` function calculates a task's priority score based on factors such as importance, urgency, due date, and completion status.

The following behaviors should be tested:

- Correct score calculation for a normal task.
- High-priority tasks receive higher scores.
- Overdue tasks receive additional score.
- Completed tasks receive lower or zero priority.
- Invalid or missing task information is handled correctly.

### Edge Cases

- Task with no due date.
- Task with negative priority.
- Task with missing fields.
- Task with very high priority.
- Empty task object.

### Test Cases

1. Verify score for a normal task.
2. Verify score for a high-priority overdue task.
3. Verify score for a completed task.
4. Verify score when the due date is missing.
5. Verify score when task data is invalid.

---

## Exercise 1.2: Test Planning

# Test Plan

## Priority of Test Cases

1. Verify calculateTaskScore().
2. Verify overdue task scoring.
3. Verify completed task scoring.
4. Verify sortTasksByImportance().
5. Verify getTopPriorityTasks().

## Types of Tests

- Unit Testing
- Integration Testing

## Test Dependencies

- Valid task objects.
- Date calculations.
- Score calculation function.

## Expected Outcomes

| Test Case | Expected Outcome |
|------------|------------------|
| Normal Task | Correct score returned |
| Overdue Task | Higher score |
| Completed Task | Lower or zero score |
| Sorting Tasks | Tasks sorted correctly |
| Top Priority | Highest scoring tasks returned |

---

# Part 2: Improving a Single Test

## Exercise 2.1: Improved Unit Test

```python
def test_calculate_task_score():
    task = {
        "priority": 5,
        "completed": False,
        "days_until_due": 2
    }

    score = calculateTaskScore(task)

    assert score > 0
```

### Improvements Made

- Clear test data.
- Tests behaviour instead of implementation.
- Uses meaningful assertions.
- Easy to read.
- Focuses on one behaviour.

---

## Exercise 2.2: Due Date Test

```python
def test_due_date_affects_score():
    task = {
        "priority": 5,
        "completed": False,
        "days_until_due": 0
    }

    score = calculateTaskScore(task)

    assert score > 5
```

### Why This Test Is Better

- Tests one behaviour only.
- Uses realistic data.
- Easy to understand.
- Detects due-date calculation errors.

---

# Part 3: Test-Driven Development (TDD)

## Exercise 3.1: TDD for a New Feature

### Requirement

Tasks assigned to the current user receive a score boost of **+12**.

### Step 1: Write the Failing Test

```python
def test_current_user_gets_bonus():
    task = {
        "priority": 5,
        "assignedToCurrentUser": True
    }

    score = calculateTaskScore(task)

    assert score >= 17
```

### Step 2: Minimal Implementation

```python
if task["assignedToCurrentUser"]:
    score += 12
```

### Step 3: Refactor

Refactor the code if needed while ensuring that all tests continue to pass successfully.

---

## Exercise 3.2: TDD for Bug Fix

### Bug

The calculation for **days since update** is incorrect.

### Test

```python
def test_days_since_update():
    task = {
        "daysSinceUpdate": 5
    }

    score = calculateTaskScore(task)

    assert score >= 0
```

### Fix

Correct the date calculation so that the number of days is calculated accurately.

---

# Part 4: Integration Testing

## Integration Test

```python
def test_task_workflow():
    tasks = [
        {"priority": 3},
        {"priority": 8},
        {"priority": 5}
    ]

    sorted_tasks = sortTasksByImportance(tasks)
    top_tasks = getTopPriorityTasks(sorted_tasks)

    assert len(top_tasks) > 0
```

### What This Test Verifies

- Task scores are calculated correctly.
- Tasks are sorted correctly.
- Top-priority tasks are returned.
- All three functions work together successfully.

---

# Discussion

## Reflection

This exercise helped me understand that testing is more than checking whether code runs successfully. Good tests verify the expected behaviour of a program and help identify bugs before software is released. I learned how to identify behaviours to test, create test plans, write better unit tests, consider edge cases, and apply Test-Driven Development (TDD). I also learned the importance of integration testing to ensure that multiple functions work together correctly. Using AI helped me think critically about testing, improve my test cases, and better understand software quality assurance.
