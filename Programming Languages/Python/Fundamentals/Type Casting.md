## **# Introduction**

- Type casting in Python is the process of converting a variable's data type into another data type.
- There are two main types of type casting in Python:
    - Implicit
    - Explicit

## **# 1. Implicit Type Casting (Automatic Conversion)**

- Python automatically converts one data type to another without user intervention.
- Happens when mixing data types in expressions, usually converting smaller or simpler types to larger or more precise types to prevent data loss.
- Example: Adding an integer and a float will convert the integer to float automatically.

```python
a = 5      *# int*
b = 3.2    *# float*
c = a + b  *# a implicitly converted to float, c is float*
print(c)   *# 8.2*
print(type(c))  *# <class 'float'>*
```

## **# 2. Explicit Type Casting (Manual Conversion)**

- The programmer explicitly converts one data type to another using built-in functions.
- Useful when input data from strings needs to be converted to numeric types, or when controlling data types in operations.
- Common casting functions:
    - `int()`: Converts float, string to integer (truncates decimals)
    - `float()`: Converts int, string to floating-point number
    - `str()`: Converts numbers or other types to string
    - Others: `tuple()`, `list()`, `set()`, `dict()` for conversions between collections

## **# Examples**

```python
*# String to int*
num_str = "10"
num_int = int(num_str)  
print(num_int, type(num_int))  *# 10 <class 'int'># Float to int*
f = 9.8
i = int(f)  
print(i)  *# 9 (decimal part truncated)# Int to float*
n = 5
f = float(n)
print(f)  *# 5.0# Number to string*
x = 100
s = str(x)
print(s, type(s))  *# '100' <class 'str'>*
```

## **# Important Points:**

- Improper or invalid type casting (e.g., `int("abc")`) raises exceptions.
- Float to int conversion truncates the decimal, does not round.
- Strings must represent valid values to convert to numbers.
- Type casting helps avoid type errors in mixed operations.