# Algorithm Deconstruction Challenge: Algorithm 3 – Task List Merging (Two-Way Sync)

## Overview

This algorithm synchronizes task lists from two different sources (a local device and a remote server). Its purpose is to merge both task lists into one consistent version while handling conflicts and ensuring that both sources stay synchronized.

---

## Purpose

The algorithm combines tasks from a local task list and a remote task list. It detects new tasks, resolves conflicts between existing tasks, and determines which tasks should be created or updated on each source.

---

## Inputs

The algorithm accepts two inputs:

- `local_tasks` – A dictionary containing tasks stored on the local device.
- `remote_tasks` – A dictionary containing tasks stored on the remote server.

---

## Outputs

The algorithm returns five values:

- `merged_tasks` – The final merged task list.
- `to_create_remote` – Tasks that should be created on the remote server.
- `to_update_remote` – Tasks that should be updated on the remote server.
- `to_create_local` – Tasks that should be created on the local device.
- `to_update_local` – Tasks that should be updated on the local device.

---

## Algorithm Breakdown

### Step 1: Initialize Data Structures

The algorithm creates empty dictionaries to store:

- Merged tasks
- Tasks to create remotely
- Tasks to update remotely
- Tasks to create locally
- Tasks to update locally

---

### Step 2: Find All Task IDs

The algorithm combines all unique task IDs from both the local and remote task lists using a set union. This ensures that every task is processed exactly once.

---

### Step 3: Compare Tasks

The algorithm loops through every task ID.

There are three possible cases:

#### Case 1: Task exists only locally

- Add the task to the merged task list.
- Mark it for creation on the remote server.

#### Case 2: Task exists only remotely

- Add the task to the merged task list.
- Mark it for creation on the local device.

#### Case 3: Task exists in both locations

The algorithm calls the `resolve_task_conflict()` function to determine which version should be kept.

---

## Conflict Resolution

The `resolve_task_conflict()` function performs the following actions:

- Creates a copy of the local task.
- Compares the `updated_at` timestamps.
- Keeps the most recently updated information.
- Gives priority to completed tasks.
- Merges tags from both versions.
- Updates the timestamp to the newest value.
- Indicates whether the local or remote version needs updating.

---

## Time Complexity

The algorithm has a time complexity of **O(n + m)**.

Where:

- **n** = Number of local tasks
- **m** = Number of remote tasks

Since every task is processed only once, the algorithm is efficient even for large task lists.

---

## Real-World Example

Imagine using a to-do list application on both your phone and your laptop.

While offline:

- You create a new task on your phone.
- You complete another task on your laptop.

When both devices reconnect to the internet, this algorithm:

- Detects new tasks.
- Copies missing tasks to the other device.
- Resolves conflicts using the latest updates.
- Preserves completed tasks.
- Merges task tags.
- Synchronizes both devices so they contain the same information.

---

## Possible Improvements

- Allow users to manually resolve conflicts.
- Maintain a history of task changes.
- Notify users when automatic conflict resolution occurs.
- Support synchronization across multiple devices instead of only two.

---

## Conclusion

This algorithm provides a reliable method for synchronizing task lists between two sources. By identifying new tasks, resolving conflicts, and updating both local and remote copies, it ensures data consistency while minimizing data loss. Its linear time complexity makes it suitable for real-world task management applications.
