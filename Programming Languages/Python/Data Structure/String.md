## **Introduction**

A **String** in Python is an immutable sequence of characters enclosed in single (`'`), double (`"`), or triple quotes (`'''` or `"""`). Strings are widely used for text processing.

## **Working Internally**

- Internally stored as a sequence of Unicode characters.
- **Immutable**: strings cannot be modified in place.
- Support indexing, slicing, and iteration.
- Concatenation creates a new string due to immutability.

## **Complexities of Common Operations**

| Operation       | Time Complexity |
| --------------- | --------------- |
| Access by Index | O(1)            |
| Concatenation   | O(n)            |
| Slicing         | O(k)            |
| Searching       | O(n)            |

## **Escape Sequences and Raw Strings**

- Special characters are represented by escape sequences, e.g.:
    - `\n` (newline), `\t` (tab), `\\` (backslash), `\'` (single quote), `\"` (double quote).
- Raw strings preserve backslashes, declared with prefix `r` or `R`:
    
    ```python
    path = r"C:\new_folder\test.txt"  *# No escape interpretation*
    ```
    

## **String Comparison**

- Strings support lexicographical comparison (`==`, `!=`, `<`, `>`, etc.).
- `in` keyword tests for substring presence.
    
    ```python
    "he" in "hello"  *# True*
    ```
    

## **String Formatting**

## **# 1. f-Strings (Python 3.6+)**

- Embeds expressions inside string literals, prefixed by `f` or `F`.
    
    ```python
    name = "Alice"
    age = 30
    print(f"{name} is {age} years old.")  *# Alice is 30 years old.*
    ```
    

## **# 2. `format()` Method**

- Uses curly braces `{}` as placeholders.
    
    ```python
    "The price is {:.2f}".format(49.99)  *# 'The price is 49.99'*
    ```
    
- Supports positional and keyword arguments:
    
    ```python
    "{0} is {1}".format("Python", "fun")
    "{lang} is awesome".format(lang="Python")
    ```
    

## **# 3. `%` Operator (Old Style)**

- Uses `%` with format specifiers like `%s`, `%d`.
    
    ```python
    "Hello, %s!" % "world"  *# Hello, world!*
    ```
    

## **Important String Methods**

| Method         | Syntax                   | Usage                                     | Example                                   |
| -------------- | ------------------------ | ----------------------------------------- | ----------------------------------------- |
| `upper()`      | `str.upper()`            | Converts all letters to uppercase         | `"hello".upper()` → `"HELLO"`             |
| `lower()`      | `str.lower()`            | Converts all letters to lowercase         | `"HELLO".lower()` → `"hello"`             |
| `title()`      | `str.title()`            | Capitalizes each word                     | `"hello world".title()` → `"Hello World"` |
| `strip()`      | `str.strip()`            | Removes leading/trailing whitespace       | `" hello ".strip()` → `"hello"`           |
| `lstrip()`     | `str.lstrip()`           | Removes leading whitespace                | `" hello ".lstrip()` → `"hello "`         |
| `rstrip()`     | `str.rstrip()`           | Removes trailing whitespace               | `" hello ".rstrip()` → `" hello"`         |
| `replace()`    | `str.replace(old,new)`   | Replaces occurrences of substring         | `"apple".replace("a","A")` → `"Apple"`    |
| `split()`      | `str.split(sep)`         | Splits into list by separator             | `"a,b,c".split(",")` → `["a","b","c"]`    |
| `join()`       | `sep.join(iterable)`     | Joins elements into string with separator | `",".join(["a","b"])` → `"a,b"`           |
| `find()`       | `str.find(sub)`          | Returns start index of substring or -1    | `"hello".find("e")` → `1`                 |
| `count()`      | `str.count(sub)`         | Counts occurrences of substring           | `"banana".count("a")` → `3`               |
| `startswith()` | `str.startswith(prefix)` | Checks if string starts with prefix       | `"hello".startswith("he")` → `True`       |
| `endswith()`   | `str.endswith(suffix)`   | Checks if string ends with suffix         | `"hello".endswith("lo")` → `True`         |

## **Immutability of Strings**

- Since strings are **immutable**, operations like concatenation or `replace()` create new strings.
- You cannot modify individual characters in place:
    
    ```python
    s = "hello"
    *# s[0] = "H"  # Raises TypeError*
    s = "H" + s[1:]  *# Correct way to modify string content*
    ```
    

## **Multiline Strings**

- Triple quotes (`'''` or `"""`) create multiline string literals or docstrings.
    
    ```python
    text = """Line 1
    Line 2
    Line 3"""
    ```
    

## **Sample Code**

```python
text = "  hello world  "

print(text.upper())              *# "  HELLO WORLD  "*
print(text.lower())              *# "  hello world  "*
print(text.title())              *# "  Hello World  "*
print(text.strip())              *# "hello world"*
print(text.lstrip())             *# "hello world  "*
print(text.rstrip())             *# "  hello world"*
print(text.replace("hello", "hi"))  *# "  hi world  "*

words = "apple,banana,cherry"
print(words.split(","))          *# ['apple', 'banana', 'cherry']*

joined = "-".join(['apple', 'banana'])
print(joined)                    *# "apple-banana"*

print(text.find("world"))        *# 8*
print(text.count("l"))           *# 3*
print(text.startswith("  he"))   *# True*
print(text.endswith("ld  "))     *# True# String formatting examples*
name = "Alice"
age = 30
print(f"{name} is {age} years old.")   *# f-string*
print("User: {}, Age: {}".format(name, age))  *# format() method*
print("User: %s, Age: %d" % (name, age))     *# % operator*
```