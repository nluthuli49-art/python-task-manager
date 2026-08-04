# Python Task Manager

## Overview

Python Task Manager is a lightweight command-line application that allows users to organize and manage their daily tasks. It provides a simple interface for creating, updating, viewing, completing, and deleting tasks while storing all information in a JSON file.

---

## Features

- Add new tasks
- View all tasks
- Edit task details
- Mark tasks as completed
- Delete tasks
- Save data automatically using JSON
- Simple and easy-to-use interface

---

## Technologies

- Python 3
- JSON
- Object-Oriented Programming (OOP)

---

## Installation

### Prerequisites

- Python 3.8 or later
- Visual Studio Code (recommended)

### Steps

1. Clone the repository.

```bash
git clone https://github.com/yourusername/python-task-manager.git
```

2. Navigate into the project.

```bash
cd python-task-manager
```

3. Run the application.

```bash
python app.py
```

---

## Usage

### Add a Task

Enter the task title, description, due date, and priority.

### View Tasks

Display all saved tasks.

### Complete Task

Select a task and mark it as completed.

### Delete Task

Choose a task and remove it permanently.

---

## Project Structure

```
task-manager/
│── app.py
│── cli.py
│── models.py
│── storage.py
│── tasks.json
└── README.md
```

### File Description

| File | Purpose |
|------|---------|
| app.py | Main application entry point |
| cli.py | User interface and menu |
| models.py | Task class and task model |
| storage.py | Saves and loads JSON data |
| tasks.json | Stores task information |

---

## Configuration

No additional configuration is required.

---

## Troubleshooting

### Python not found

Ensure Python is installed and added to your system PATH.

### Tasks are not saving

Check that the `tasks.json` file exists and the application has permission to write to it.

### Import errors

Ensure all project files are in the same project folder.

---

## Future Improvements

- Task categories
- User authentication
- Search functionality
- Notifications
- Graphical User Interface (GUI)

---

## Contributing

Contributions are welcome. Please fork the repository, make improvements, and submit a pull request.

---

## License

This project is for educational purposes.
