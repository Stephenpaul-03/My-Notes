## **Introduction**

- Comments in Python are text notes written within the code to explain, clarify, or document portions of the program for human readers.
- They are ignored by the Python interpreter and do not affect program execution.

## **Types of Comments in Python**

## **# 1. Single-Line Comments**

- Start with the hash symbol `#`.
- Everything after `#` on the same line is treated as a comment.
- Used for brief explanations or annotations on a single line.

Example:

```python
*# This is a single-line comment*
print("Hello, World!")  *# Comment at the end of a code line*
```

## **# 2. Multi-Line Comments**

- Python does not have a distinct multi-line comment syntax.
- To comment multiple lines, use `#` at the beginning of each line.
- Alternatively, triple-quoted strings (`''' ... '''` or `""" ... """`) can be used as multi-line comments but technically they are multi-line string literals not assigned to any variable, so Python ignores them.
- Useful for longer explanations or temporarily disabling blocks of code.

Examples:

```python
*# This is a multi-line comment# and Python ignores everything here# until the last line*

"""
This is a multi-line string,
which can also serve as a comment.
It won't be executed unless used in code.
"""
```

## **# 3. Docstrings (Documentation Strings)**

- Special type of multi-line comment placed immediately after a function, method, module, or class definition.
- Enclosed in triple quotes and used to describe what the function/class/module does.
- Can be accessed at runtime using the `__doc__` attribute or help system.
- Useful for documentation and code readability.

Example:

```python
def greet(name):
    """
    This function greets to the person
    passed in as parameter name.
    """
    print(f"Hello, {name}!")

print(greet.__doc__)  *# Access the docstring*
```

## **Importance and Best Practices**

- Comments make code more readable and maintainable.
- Help other programmers or future self to understand the logic and intent.
- Use comments to explain why, not what (avoid obvious comments).
- Keep comments concise and meaningful.
- Use docstrings effectively in functions and classes for auto-generated documentation.