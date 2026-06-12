# 4. Python Syntax Reading Material for Screen Reader Users

## Observation

During in-class support, it was observed that NVDA does not consistently announce certain punctuation characters when reading Python code aloud. For example, quotation marks (`"` and `'`) are frequently skipped, which means a student cannot tell by ear whether a value is a string or a bare word. 

Because sighted students can glance at code and immediately see its structure, they build an intuitive understanding of syntax visually. A screen reader user does not have this passive exposure, so providing a consolidated reference of Python structural rules may help before she begins the coding exercises.

## “Reading Python Out Loud” page
https://earth-ds-ml.github.io/summer_2026/accessible/lectures_DS/core_python/reading_python_out_loud.html




## Proposed Addition (via working with Claude) - Covered in the new webpage

### 1. Common Python symbols and what they mean

A short reference describing the symbols a student will encounter most often, written out in words rather than shown visually. For example:

- The equals sign `=` assigns a value to a variable. For example, `x = 5` means "x is assigned the value 5."
- Double equals `==` checks whether two values are the same. For example, `x == 5` asks "is x equal to 5?"
- A colon `:` at the end of a line (after `if`, `for`, `def`, etc.) signals that an indented block follows.
- Indentation (4 spaces at the start of a line) means that line belongs to the block above it.
- Quotation marks `"` or `'` wrap a string value. Both single and double quotes work; they must match. For example, `"hello"` and `'hello'` are the same.
- Parentheses `()` follow a function name and contain its arguments. For example, `print("hello")` calls the print function with the argument `"hello"`.
- Square brackets `[]` define a list or access an item by position. For example, `[1, 2, 3]` is a list, and `my_list[0]` gets the first item.
- Curly braces `{}` define a dictionary. For example, `{"name": "Laras", "year": 2024}`.
- The hash symbol `#` starts a comment. Everything after it on that line is ignored by Python.

### 2. Variable naming conventions

A short explanation of how variables are named in Python, so the student can recognise and write variable names confidently:

- Variable names are case-sensitive: `myData` and `mydata` are different variables.
- Variable names cannot contain spaces. Use an underscore to separate words: `my_variable`, `co2_data`.
- Variable names should be lowercase by convention (e.g. `temperature`, not `Temperature`).
- Variable names cannot start with a number: `2data` is invalid, `data2` is valid.
- Avoid using Python's reserved words as variable names (e.g. `list`, `print`, `for`, `if`).
- Descriptive names are preferred over single letters, except in short loops (e.g. `for i in range(10)`).
