# Expense Tracker

A menu-driven Java console app for tracking personal expenses .

## Features

- Add new expenses with date, description, amount, and category.
- Update and delete existing expenses.
- View all expenses.
- View a summary of all expenses, or for a specific month.
- Filter expenses by category and see the category total.
- Set a monthly budget and get warned when a month's spend goes over it
  (budgets persist to `budgets.txt`).
- Export all expenses to a CSV file (`expenses_export.csv`), with fields quoted
  so commas in descriptions don't break the file.
- Expenses persist to a file (`expenses.txt`) between runs; descriptions with
  commas are quoted so the save file round-trips safely.

Planned extensions from the roadmap.sh spec are tracked as [good first issues](https://github.com/chaudhary-lakshay/Expense-Tracker/issues) — contributions welcome.

## Project structure

```
src/Expense_Tracker/
├── Expense.java          # expense model: date, description, amount, category
├── ExpenseStorage.java   # saves/loads expenses to expenses.txt
├── BudgetStorage.java    # saves/loads monthly budgets to budgets.txt
├── CsvUtil.java          # shared CSV escaping/parsing (safe for commas & quotes)
├── CsvUtilTest.java      # runnable self-check for CSV round-tripping
└── ExpenseTracker.java   # main class, menu loop, all commands
```

## Run it

```bash
git clone https://github.com/chaudhary-lakshay/Expense-Tracker.git
cd Expense-Tracker/src
javac Expense_Tracker/*.java
java Expense_Tracker.ExpenseTracker
```

Requires JDK 8+.
