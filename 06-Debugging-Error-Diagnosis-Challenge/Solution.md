# Solution

## Error Description

The application displays the following error:

```text
IndexError: list index out of range
```

This happens because the program attempts to access a list index that does not exist. The loop runs one extra iteration, causing Python to reference an element beyond the end of the list.

---

## Root Cause

The loop is written as:

```python
for i in range(len(items) + 1):
```

The `+ 1` causes the loop to continue one step beyond the last valid index. Since Python lists are zero-indexed, the last valid index is `len(items) - 1`.

---

## Solution

Remove the `+ 1` so the loop only iterates through valid indexes.

**Incorrect code:**

```python
for i in range(len(items) + 1):
    print(items[i]["name"], items[i]["quantity"])
```

**Correct code:**

```python
for i in range(len(items)):
    print(items[i]["name"], items[i]["quantity"])
```

An even better solution is to loop through the list directly:

```python
for item in items:
    print(item["name"], item["quantity"])
```

---

## Learning Points

- Python lists use zero-based indexing.
- The last valid index is always one less than the length of the list.
- Using `range(len(list))` prevents out-of-range errors.
- Reading error messages and tracebacks helps identify the source of bugs.
- Iterating directly over list items is often simpler and less prone to errors than using indexes.
