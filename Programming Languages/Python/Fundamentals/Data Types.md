## **# **Numeric Types****

- **int:** Integer values, positive or negative whole numbers without a fractional component. Example: `5, -3, 1000`.
- **float:** Floating-point (decimal) numbers. Example: `3.14, -0.001, 2.0`.
- **complex:** Complex numbers consisting of a real and an imaginary part. Example: `3 + 4j`.

## **# **Text Type****

- **str:** String type for text data, enclosed in single quotes, double quotes, or triple quotes. Supports Unicode. Example: `"Hello"`, `'Python'`.

## **# **Sequence Types****

- **list:** Mutable ordered sequences of elements, defined using square brackets. Can hold mixed data types. Example: `[1, 'two', 3.0]`.
- **tuple:** Immutable ordered sequences, defined with parentheses. Example: `(1, 2, 3)`.
- **range:** Immutable sequences of numbers commonly used in loops. Example: `range(0, 10)`.

## **# **Mapping Type****

- **dict:** Unordered collections of key-value pairs, defined by curly braces with keys and values separated by colons. Keys must be immutable. Example: `{"name": "Alice", "age": 25}`.

## **# **Set Types****

- **set:** Unordered collections of unique, mutable elements. Example: `{1, 2, 3}`.
- **frozenset:** Immutable version of a set.

## **# **Boolean Type****

- **bool:** Represents truth values `True` and `False`. Frequently used in conditional expressions.

## **# **Binary Types****

- **bytes:** Immutable sequences of bytes.
- **bytearray:** Mutable sequences of bytes.
- **memoryview:** A memory view object to access the internal data of an object supporting the buffer protocol without copying.

## **# **None Type****

- **NoneType:** Represents the absence of a value, mainly used to signify "no value" or "null". Example: `None`.

## **Examples**

```python
*# Numeric Types*
x = 42          *# int*
y = 3.14        *# float*
z = 1 + 2j      *# complex# Text Type*
name = "Python"

*# Sequence Types*
letters = ['a', 'b', 'c']  *# list*
coords = (10, 20)          *# tuple*
nums = range(5)            *# range# Mapping Type*
person = {"name": "Bob", "age": 30}

*# Set Types*
unique_numbers = {1, 2, 3}
immutable_set = frozenset([4, 5, 6])

*# Boolean Type*
is_active = True

*# Binary Types*
b = b'hello'
ba = bytearray(b'world')

*# None Type*
nothing = None
```

## **Important Characteristics**

- **Mutability:** Mutable types like lists and sets can be changed after creation. Immutable types like strings, tuples, and frozensets cannot be altered once created.
- **Ordering:** Lists, tuples, and ranges preserve order. Sets and dictionaries (as of Python 3.7+) preserve insertion order, but sets traditionally are unordered.
- **Uniqueness:** Sets store unique elements only.
- **Indexing and Slicing:** Sequences support indexing and slicing; mappings use keys for access.
- **Data Type Checking:** Use `type()` to determine the type of any object.

## **Type Conversion**

Python provides functions to explicitly convert between types:

```python
int("10")     *# from string to int*
float(5)      *# from int to float*
str(123)      *# from int to string*
list((1, 2))  *# from tuple to list*
```