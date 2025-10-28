## **Introduction**

- Python error handling is performed using exceptions, which are runtime errors that interrupt normal program flow.
- Python provides a powerful syntax using `try`, `except`, `else`, and `finally` blocks to handle exceptions gracefully.

## **Key Components of Error Handling**

## **# 1. try Block**

- Contains code that might raise an exception.
- Executes normally if no exceptions occur.

## **# 2. except Block**

- Defines how to handle specific exceptions.
- Can specify particular exception types.
- Runs only if an exception occurs in the corresponding `try` block.

## **# 3. else Block (Optional)**

- Executes if no exceptions are raised in the `try` block.
- Useful for code that should run only when no errors occur.

## **# 4. finally Block (Optional)**

- Executes no matter what, whether an exception occurred or not.
- Typically used for cleanup actions (e.g., closing files).

## **Raising Exceptions**

You can raise exceptions deliberately using `raise`:

```python
def check_age(age):
    if age < 0:
   ode  raise ValueError("Age cannot be negative")
```

## **Custom Exceptions**

Define your own exception types by inheriting from `Exception`:

```python
class CustomError(Exception):
    pass

raise CustomError("This is a custom error")
```

## **Basic Syntax**

```python
try:
    *# Code that may raise an exception*
except SomeException as e:
    *# Code to handle the exception*
else:
    *# Code to execute if no exception occurs*
finally:
    *# Code to execute regardless of exceptions*
```

## **Example**

```python
try:
    x = 10 / 0
except ZeroDivisionError as e:
    print(f"Caught an error: {e}")
else:
    print("No errors occurred!")
finally:
    print("Execution completed.")
```

Output:

`Caught an error: division by zero
Execution completed.`

## **Exceptions**

| Exception Name | Description | How to Trigger Example |
| --- | --- | --- |
| **ZeroDivisionError** | Division by zero | `10 / 0` |
| **TypeError** | Operation on incompatible types | `'2' + 3` |
| **ValueError** | Wrong value type (e.g., invalid literal) | `int('abc')` |
| **IndexError** | Index out of range in sequences | `[1, 2, 3][10]` |
| **KeyError** | Missing key in dictionary | `{'a':1}['b']` |
| **AttributeError** | Object has no such attribute | `''.foo` |
| **NameError** | Using undefined variable | `print(x)` (if `x` not defined) |
| **FileNotFoundError** | Trying to open a non-existent file | `open('nofile.txt')` |
| **ImportError** | Importing a non-existent module | `import nonexistmodule` |
| **StopIteration** | Raised by `next()` on exhausted iterator | `next(iter([]))` |
| **IndentationError** | Incorrect block indentation | Improperly indented code |
| **SyntaxError** | Invalid Python syntax | `eval('x === 2')` |
| **EOFError** | End of file when input() has no data | Calling `input()` when no input available |
| **MemoryError** | System runs out of memory | Large memory allocation, e.g., `[0]*10**10` |
| **UnboundLocalError** | Referencing local variable before assignment | Using variable before it’s assigned in function |
| **RecursionError** | Exceeded maximum recursion depth | Infinite recursive function call |
| **OverflowError** | Numerical operation too large to represent | `2.0 ** 10000` |
| **FloatingPointError** | Floating-point operation error | Rare, e.g., floating point underflow |
| **AssertionError** | Assert statement failed | `assert 1 == 0` |
| **KeyboardInterrupt** | User interrupts program (Ctrl+C) | Press Ctrl+C during program execution |

## **Examples**

```python
*# ZeroDivisionError*
try:
    1 / 0
except ZeroDivisionError as e:
    print(e)

*# TypeError*
try:
    '2' + 3
except TypeError as e:
    print(e)

*# ValueError*
try:
    int("abc")
except ValueError as e:
    print(e)

*# IndexError*
try:
    [1, 2, 3][10]
except IndexError as e:
    print(e)

*# KeyError*
try:
    d = {'a': 1}
    print(d['b'])
except KeyError as e:
    print(e)

*# AttributeError*
try:
    ''.foo()
except AttributeError as e:
    print(e)
```