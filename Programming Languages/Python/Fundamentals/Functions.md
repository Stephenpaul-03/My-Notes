## **Introduction**

- Functions in Python are reusable blocks of code designed to perform a specific task.
- They help organize code into modular chunks, which makes programs easier to read, maintain, and debug.

## **Defining Functions**

- Use the `def` keyword followed by the function name and parentheses `()`.
- Optional parameters can be included inside the parentheses.
- The function body is indented below the header and can include statements, expressions, and an optional `return` statement.
- Functions may have a docstring (enclosed in triple quotes) immediately after the header to describe the function purpose.

## **Calling Functions**

Invoke the function by its name followed by parentheses. Pass any required arguments matching the parameters.

```python
greet("Bob")  *# Hello, Bob!*
```

## **Return Statement**

- Functions can return values using `return`.
- Returning exits the function immediately.
- Without `return`, functions implicitly return `None`.

```python
def multiply(a, b):
    return a * b

result = multiply(4, 5)
print(result)  *# 20* 
```

## **Function Parameters and Arguments**

1. **Positional Arguments:** Passed in the order of parameters.
2. **Keyword Arguments:** Passed with parameter names, order doesn't matter.
3. **Default Arguments:** Parameters with default values if arguments are not provided.
4. **Variable-Length Arguments:**
    - Use `args` for arbitrary number of positional arguments.
    - Use `*kwargs` for arbitrary number of keyword arguments.

```python
#Positional Arguments
def add(a, b):
    return a + b

print(add(3, 5))  *# 8*

#Keywords Arguments
**def print_info(name, age):
    print(f"Name: {name}, Age: {age}")

print_info(age=30, name="John")

#Default Arguments
def greet(name="Guest"):
    print(f"Hello, {name}!")

greet()          *# Hello, Guest!*
greet("Alice")   *# Hello, Alice!*

#Variable-Length Arguments

#args
**def sum_all(*args):
    return sum(args)
    
print(sum_all(1, 2, 3, 4, 5))  *# 15*

#*kwargs
**def print_details(**kwargs):
    for key, value in kwargs.items():
        print(f"{key}: {value}")
        
print_details(name="Alice", age=30, city="NY")
```

## **Lambda Functions**

- also known Anonymous Functions
- Small one-expression functions declared with `lambda`.
- Used for short, throwaway functions.

```python
add = lambda x, y: x + y
print(add(3, 5))  *# 8*
```

## **Recursive Functions**

- Functions that call themselves to solve problems via repeated breakdown.

```python
def factorial(n):
    if n == 1:
        return 1
    else:
        return n * factorial(n - 1)

print(factorial(5))  *# 120*
```

## **Syntax**

```python
def function_name(parameters):
    """Docstring explaining the function"""
    *# Function body*
    return value  *# Optional*
```

## **Example**

```python
def greet(name):
    """Prints a greeting to the provided name."""
    print(f"Hello, {name}!")

greet("Alice")  *# Output: Hello, Alice!*
```