# Exercise Submission – Knowing Where to Start

## 1. Initial vs. Final Understanding

### Initial Understanding
At first, I only knew that the project was a Python Task Manager. I did not know how the files worked together or where new features should be added.

### Final Understanding
After exploring the project, I learned that the application is organized into separate files with different responsibilities. The main entry point is `app.py`, `models.py` contains the task data and business logic, `storage.py` handles saving and loading data, and `cli.py` manages user interaction. I now have a better understanding of how the different components work together.

---

## 2. Most Valuable Insights from Each Prompt

- **Project Structure Prompt:** Helped me identify the main files and their responsibilities.
- **Feature Location Prompt:** Helped me determine where a new feature should be implemented and which files would need changes.
- **Domain Model Prompt:** Helped me understand the main entities such as Task, TaskStatus, and TaskPriority and how they relate.
- **Practical Application Prompt:** Showed me how to plan a feature before writing code and think about implementation details.

---

## 3. My Approach to Implementing the New Business Rule

To implement the rule that tasks overdue by more than seven days should be marked as abandoned unless they are high priority, I would:

- Check each task's due date.
- Compare the due date with the current date.
- Skip tasks marked as high priority.
- Update overdue tasks to the "Abandoned" status.
- Save the changes using the storage component.
- Display the updated status in the user interface.
- Test the feature with different task scenarios.

---

## 4. Strategies for Approaching Unfamiliar Code in the Future

In the future I will:

- Start by exploring the project structure.
- Read the README and configuration files first.
- Identify the main entry point of the application.
- Understand the purpose of each file before making changes.
- Use AI to explain unfamiliar code and answer questions.
- Test my understanding before implementing new features.
- Make small changes and test them regularly.

## Conclusion

This exercise helped me understand how to explore an unfamiliar codebase before making changes. I also learned how AI can assist in understanding project structure, locating features, understanding business logic, and planning implementations without immediately changing the code.
