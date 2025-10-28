## **Introduction**

- Loops in Python allow repeated execution of a block of code as long as a specified condition is met or for a specific number of iterations.
- They are essential for automating repetitive tasks and iterating over collections.
- There are mainly two types of loops in Python:
    - `for` loops
    - `while` loops

## **For Loop**

- Used to iterate over a sequence (like list, tuple, string, dictionary, set) or any iterable.
- Executes the code block once for each item in the sequence.
- The `else` block after a loop runs if the loop completes without encountering a `break`.
- Syntax:
    
    ```python
    for variable in sequence:
        *# code to execute*
    ```
    
- **Examples:**
    
    ```python
    *# Iterate through a list*
    fruits = ["apple", "banana", "cherry"]
    for fruit in fruits:
        print(fruit)
    
    *# Iterate through a string*
    for letter in "Python":
        print(letter)
    
    *# Using range() to loop over a sequence of numbers*
    for i in range(5):
        print(i)
        
     for i in range(3):
        print(i)
    else:
        print("Loop finished without break")
    ```
    
- The `range()` function generates a sequence of numbers useful for loop iteration.
- Supports parameters like `range(start, stop, step)`.

## **While Loop**

- Repeats a block of code as long as a specified condition evaluates to True.
- The `else` block runs when the loop condition becomes False (and no break occurs).
- Syntax:

```python
while condition:
    *# code to execute*
```

- Examples:

```python
count = 0
while count < 5:
    print(count)
    count += 1
    
## **Remember to update the condition variable inside the loop to avoid infinite loops.**

i = 0
while i < 3:
    print(i)
    i += 1
else:
    print("While loop completed")
```

## **Nested Loops**

- A loop inside another loop.
- The inner loop executes completely for each iteration of the outer loop.
- Example

```python
for i in range(3):
    for j in range(2):
        print(f"i = {i}, j = {j}")
 # While loop nested inside for loop (or vice versa) is also valid.
```

## **Loop Control Statements**

- **break:** Terminates the loop immediately.
- **continue:** Skips the current iteration and proceeds with the next one.
- **pass:** A null statement, used as a placeholder in loops with no action.

```python
for i in range(5):
    if i == 3:
        break
    print(i)
    
for i in range(5):
    if i == 3:
        continue
    print(i)
    
for i in range(5):
    pass  *# To be implemented later*
```