# Part 2 – Finding Feature Implementation

## Scenario
My team lead asked me to add a new feature called **Task Export to CSV**. Before implementing it, I needed to understand how similar features are implemented in the project.

## 1. Initial Search

### Existing export or file-related functionality
I searched the project for code related to exporting data, saving files, and reading or writing files. I looked for existing functionality that handles task storage.

### Data transformation or file operations
I found that the storage component is responsible for handling file operations such as saving and loading task data. This is the most appropriate place for file-related features.

### Reusable utility functions
The existing storage functions appear to be reusable because they already work with task data and file operations.

---

## 2. Form a Hypothesis

### Where the Task Export to CSV feature belongs
I believe the Task Export to CSV feature should be implemented in `storage.py` because it is responsible for reading and writing task data. The `cli.py` file should provide an option for users to export tasks, while `app.py` should coordinate the application flow if necessary.

### Components that may need to be modified
- `storage.py` – Add a function to export tasks to a CSV file.
- `cli.py` – Add a new command or menu option for exporting tasks.
- `app.py` – Update the application flow if required.

### Search terms used
- export
- csv
- save
- file
- storage
- write
- task

### Files examined
- `storage.py`
- `cli.py`
- `app.py`
- `models.py`

---

## 3. Apply the Feature Location Prompt

### Prompt Used
I need to add a new feature called **Task Export to CSV**. Based on the existing Task Manager project, help me identify where this feature should be implemented. I examined the project structure and found files such as `app.py`, `cli.py`, `models.py`, and `storage.py`. Which components should be modified, and are there any existing patterns or similar features that I can reuse?

### Search Approach and Findings
I searched for code related to:
- File operations
- Data storage
- Task management
- Saving and loading data

I found that `storage.py` handles file operations, while `cli.py` manages user interaction.

### Guidance from AI
The AI suggested implementing the CSV export functionality in `storage.py` and adding an **Export to CSV** option in `cli.py` so users can export their tasks.

---

## 4. Document My Findings

### Where I would implement the feature
I would implement the CSV export feature mainly in `storage.py` because it already manages task data and file operations. The `cli.py` file would be updated to include an **Export to CSV** option.

### Related components
- `storage.py`
- `cli.py`
- `app.py`
- `models.py`

### Implementation Plan
1. Add a function that exports tasks to a CSV file.
2. Add an Export to CSV option to the command-line interface.
3. Connect the CLI option to the export function.
4. Test the feature to ensure the CSV file is created correctly and contains all task information.

