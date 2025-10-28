## **Introduction**

- Conditional statements in Python allow a program to execute certain blocks of code based on whether a condition or set of conditions is true or false.
- They enable decision-making in code, making programs adaptable to different inputs or situations.

## **Main Types of Conditional Statements**

## **# 1. If Statement**

- The simplest form: executes a block of code only if the given condition evaluates to True.
- Syntax:

```python
if condition:
    *# code to execute if condition is True*
```

Example:

```python
age = 20
if age >= 18:
    print("Eligible to vote.")
```

## **# 2. If-Else Statement**

- Provides an alternative block of code executed if the condition is False.
- Syntax:

```python
if condition:
    *# execute this when True*
else:
    *# execute this when False*
```

Example:

```python
age = 16
if age >= 18:
    print("Eligible to vote.")
else:
    print("Not eligible to vote.")
```

## **# 3. If-Elif-Else Statement**

- Allows checking multiple conditions in sequence.
- The first condition that evaluates to True executes its block; others are skipped.
- Syntax:

```python
if condition1:
    *# code block 1*
elif condition2:
    *# code block 2*
else:
    *# code block if all conditions fail*
```

Example:

```python
marks = 85
if marks >= 90:
    print("Grade A")
elif marks >= 80:
    print("Grade B")
else:
    print("Grade C or below")
```

## **# 4. Nested If Statements**

- If statements placed inside another if or else block for more complex logic.

Example:

```python
num = 10
if num > 0:
    if num % 2 == 0:
        print("Positive even number")
    else:
        print("Positive odd number")
else:
    print("Non-positive number")
```

## **# 5. Short Hand If and If-Else (Ternary Operator)**

- Compact syntax for simple conditional expressions.
- Short hand if:

```python
if age > 18: print("Adult")
```

- Ternary operator (conditional expression):

```python
status = "Adult" if age >= 18 else "Minor"
print(status)
```

## **Important Notes**

- Python uses indentation (typically 4 spaces) to define code blocks inside conditional statements.
- Conditions can use all standard comparison operators (`==`, `!=`, `>`, `<`, `>=`, `<=`) and logical operators (`and`, `or`, `not`).
- The `elif` and `else` blocks are optional, but only one `else` block is allowed per if chain.
- Python 3.10+ introduced the `match-case` statement, similar to switch-case found in other languages, for pattern matching.