# Algorithm 2: Task Text Parser

## Purpose
This algorithm converts free-form text into a structured task object.

### Example Inputs
- Buy milk @shopping !2 #tomorrow
- Finish report for client XYZ !urgent #friday @work @project

---

## Step-by-Step Explanation

### 1. Set Default Values
The algorithm starts by creating default task properties.

- Title = the full text entered by the user
- Priority = MEDIUM
- Due date = None
- Tags = empty list

---

### 2. Extract Priority

The algorithm searches the text for a priority marker.

It accepts either:

- !1
- !2
- !3
- !4

or

- !low
- !medium
- !high
- !urgent

Once found it:

- removes the priority marker from the title
- converts it into the correct priority level

Example:

Input:

Buy milk !urgent

Result:

Priority = URGENT

---

### 3. Extract Tags

The algorithm searches for words beginning with **@**

Example:

@shopping

@work

@project

Every tag found is:

- stored inside a list
- removed from the task title

Example

Input:

Buy milk @shopping

Result

Title:

Buy milk

Tags:

shopping

---

### 4. Extract Due Date

The algorithm searches for words beginning with **#**

Examples:

- #today
- #tomorrow
- #nextweek
- #monday
- #friday
- #2026-08-01

The date marker is removed from the title.

The algorithm then converts it into an actual date.

Examples:

today → today's date

tomorrow → today + 1 day

nextweek → today + 7 days

monday → next Monday

2026-08-01 → exact date

---

### 5. Clean the Title

After removing priorities, tags and dates, extra spaces are removed.

Example

Before:

Buy milk @shopping !urgent

After:

Buy milk

---

### 6. Create the Task Object

Finally the algorithm creates a new Task.

It stores:

- title
- priority
- due date
- tags

Then returns the completed task object.

---

## Summary

The algorithm performs six main steps:

1. Set default task values.
2. Find and process priority.
3. Find and process tags.
4. Find and process due dates.
5. Clean the task title.
6. Return the completed task object.

---

## Time Complexity

- Searching for priorities: O(n)
- Searching for tags: O(n)
- Searching for dates: O(n)
- Cleaning text: O(n)

Overall Time Complexity:

**O(n)**

where **n** is the length of the input text.

---

## Space Complexity

The algorithm stores:

- title
- tags
- due date
- priority

Space Complexity:

**O(n)**

because the tags and cleaned text require additional memory.
