# Exercise 10– Function Decomposition Challenge

## Objective

The goal of this exercise was to improve a complex function by breaking it into smaller helper functions. This makes the code easier to read, test, maintain, and reuse while keeping the same functionality.

---

## Part 1: Responsibilities Identified

The original function had multiple responsibilities, including:

- Validating user input.
- Checking required fields.
- Processing and transforming data.
- Handling errors.
- Generating reports.
- Formatting output.
- Returning results.

Because all of these tasks were inside one function, the code was difficult to read and maintain.

---

## Part 2: Decomposition Plan

The large function was divided into smaller helper functions with clear responsibilities.

### Helper Functions

- `validateInput()`
- `checkRequiredFields()`
- `processData()`
- `generateReport()`
- `formatOutput()`
- `handleErrors()`

The main function now calls these helper functions in sequence, making the code much cleaner and easier to understand.

---

## Part 3: Refactoring

The original function was refactored by moving each responsibility into its own helper function.

### Improvements

- Each function has one responsibility.
- The code is easier to read.
- The code is easier to maintain.
- Helper functions can be reused.
- Future updates are simpler.
- Testing individual functions is easier.

---

## Part 4: Testing

The refactored function was tested to ensure that it still behaved exactly the same as the original version.

### Test Results

- ✅ Input validation works correctly.
- ✅ Required fields are checked correctly.
- ✅ Invalid data returns appropriate errors.
- ✅ Valid data is processed successfully.
- ✅ Output remains unchanged after refactoring.

---

## Part 5: Benefits

Breaking the function into smaller helper functions provided several benefits:

- Improved readability.
- Better maintainability.
- Easier debugging.
- Easier testing.
- More reusable code.
- Cleaner structure.
- Simpler future enhancements.

---

# Reflection Questions

## 1. How did breaking down the function improve its readability and maintainability?

Breaking the function into smaller helper functions made the code easier to understand because each function performs one specific task. This also makes debugging, testing, and future maintenance much easier.

---

## 2. What was the most challenging part of decomposing the function?

The most challenging part was identifying where to split the responsibilities without changing the original behaviour of the function.

---

## 3. Which extracted function would be most reusable in other contexts?

The `validateInput()` function would be the most reusable because validating user input is required in many different software applications.

---

## Conclusion

This exercise demonstrated how function decomposition improves software quality by creating cleaner, more organized, and maintainable code while preserving the original functionality.
