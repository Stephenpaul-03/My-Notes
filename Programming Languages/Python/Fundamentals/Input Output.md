## **# Input in Python**

- The built-in function `input()` is used to take input from the user via the keyboard.
- The function optionally takes a prompt string to display a message to the user.
- `input()` always returns the user input as a string.
- For numerical or other data types, the string input must be explicitly converted using type casting functions like `int()`, `float()`, etc.
- Multiple inputs can be taken in one line by using the `split()` method to separate values and unpacking them into variables.

## **# Example**

```python
name = input("Enter your name: ")
print("Hello", name)

age = int(input("Enter your age: "))
print("You are", age, "years old")

*# Taking multiple inputs*
x, y = input("Enter two numbers: ").split()
x = int(x)
y = int(y)
print("Sum:", x + y)
```

## **# Output in Python**

- The `print()` function is used to display output on the console.
- It can take multiple arguments separated by commas and print them with a space by default.
- It has useful parameters:
    - `sep`: Specifies the separator between multiple objects (default space).
    - `end`: Specifies what to print at the end (default newline `\n`).
- Supports formatted string literals (f-strings) for embedding variable values inside strings, improving readability.

## **# Examples**

```python
print("Hello", "World")             *# Output: Hello World*
print("Hello", "World", sep="-")    *# Output: Hello-World*
print("Hello", end=", ")            *# Output: Hello,*
print("World")                     *# Output: World# Formatted string output*
name = "Alice"
age = 30
print(f"{name} is {age} years old.")  *# Output: Alice is 30 years old.*
```

## **Important Points**

- Use explicit casting when expecting numerical input from users.
- `input()` pauses program execution until user input is provided.
- `print()` converts non-string objects to strings automatically.
- Output can be customized using `sep`, `end`, and formatting options.