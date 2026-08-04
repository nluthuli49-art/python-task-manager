# Error Analysis

## Selected Error

**Off by One Error (Python)**

## Error Description

The program crashes with the following error:

```text
IndexError: list index out of range
```

This error occurs when the program tries to access a list element that does not exist. In the provided code, the loop runs one extra time, causing Python to look for an item beyond the end of the list.

## Root Cause

The problem is caused by the following loop:

```python
for i in range(len(items) + 1):
```

Adding `+ 1` makes the loop iterate one time too many. When `i` becomes equal to the length of the list, Python attempts to access `items[i]`, which is outside the valid index range.

## Suggested Solution

Remove the `+ 1` so that the loop only iterates through valid indexes.

**Incorrect code:**

```python
for i in range(len(items) + 1):
```

**Correct code:**

```python
for i in range(len(items)):
```

An even better approach is to iterate directly over the list:

```python
for item in items:
    print(item["name"], item["quantity"])
```

## Learning Points

- Python list indexes start at **0**.
- The last valid index is **length - 1**.
- Avoid adding unnecessary values to `range()`.
- Reading the traceback helps identify where an error occurred.
- Iterating directly over list items is often safer than using indexes
