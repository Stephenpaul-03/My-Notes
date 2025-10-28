## **# Introduction**

- Variables in Python are symbolic names that refer to objects or values stored in memory.
- They serve as placeholders to store data that can be referenced, manipulated, and reused during program execution.
- Python does not require explicit type declaration for variables;
- the type is inferred dynamically depending on the assigned value.

## **# Key Points**

- Variables are created by assigning a value with the assignment operator `=`.
- Variable names can contain letters, digits, and underscores but cannot start with a digit.
- Variable names are case-sensitive (`myVar` and `myvar` are distinct).
- You cannot use Python reserved keywords (like `if`, `else`, `for`) as variable names.
- Variables are dynamically typed; the same variable can hold values of different types at different times.
- You can assign multiple variables at once either with the same value or different values.
- Variables can refer to any Python objects including numbers, strings, lists, dictionaries, functions, classes, or custom objects.

## **# Examples**

```python
x = 5                    *# integer assignment*
name = "Samantha"         *# string assignment*
a = b = c = 100           *# multiple variables same value*
x, y, z = 1, 2.5, "Hi"   *# multiple variables different values*

x = 10                    *# dynamic typing - now x is integer*
x = "Now a string"        *# dynamic typing - now x holds a string*
```

## **# Variable Naming Rules:**

- Names must start with a letter or underscore (_).
- Can contain letters, digits, or underscores.
- Should follow snake_case convention for readability.
- Avoid names that shadow built-in functions or keywords.

## **# Usage and Importance**

- Variables make code readable and maintainable by using descriptive names instead of raw values.
- They enable reuse of values without repeating literals.
- Facilitates operations like swapping, temporary storage, and results storage.
- Used in expressions, calculations, control flow, and data manipulation.

## **# Scope and Lifetime**

- Variables can have different scopes:
    - local (inside functions)
    - global (module-level)
    - nonlocal (enclosed functions).
- The scope affects where the variable can be accessed and modified.