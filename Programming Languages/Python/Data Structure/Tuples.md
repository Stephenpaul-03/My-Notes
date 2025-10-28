## **Introduction**

A **Tuple** in Python is an ordered, immutable collection of elements. Once created, you cannot change, add, or remove its elements.

## **Working Internally**

- Stored as a fixed-size array.
- Supports indexing, slicing, and iteration.
- Immutable → safer and hashable (can be used as dictionary keys).
- Length is stored internally for fast length retrieval.

## **Complexities of Common Operations**

| Operation       | Time Complexity                          |
| --------------- | ---------------------------------------- |
| Access by Index | O(1) (constant time)                     |
| Search          | O(n) (linear search)                     |
| Iteration       | O(n)                                     |
| Concatenation   | O(k + n) (where k and n are tuple sizes) |
| Length          | O(1)                                     |
| Slicing         | O(k) (where k is slice length)           |

## **Common Tuple Methods**

| Method    | Syntax              | Usage                      | Example                       |
| --------- | ------------------- | -------------------------- | ----------------------------- |
| `count()` | `tuple.count(item)` | Counts occurrences of item | `(1, 2, 3, 2).count(2)`  → 2  |
| `index()` | `tuple.index(item)` | Returns index of item      | `(1, 2, 3).index(3)`      → 2 |

## **Additional Operations on Tuples**

- **Concatenation**: Use `+` operator to combine tuples:
    
    ```python
    1 = (1, 2)
    t2 = (3, 4)
    t3 = t1 + t2  *# (1, 2, 3, 4)*
    ```
    
- **Repetition**: Use  operator to repeat tuples:
    
    ```python
    t = (1, 2)
    t3 = t * 3  *# (1, 2, 1, 2, 1, 2)*
    ```
    
- Both operations produce *new* tuples since tuples are immutable.

## **Important Notes**

- Tuples’ immutability makes them ideal for fixed collections of heterogeneous data.
- They can be used as keys in dictionaries due to hashability.
- Support all sequence operations except for in-place modification (like assignment or deletion).
- Useful in functions for returning multiple values.

## **Example Code**

```python
t = (1, 2, 3, 2)

print(t.count(2))      *# 2*
print(t.index(3))      *# 2# Tuple concatenation*
t1 = (1, 2)
t2 = (3, 4)
print(t1 + t2)         *# (1, 2, 3, 4)# Tuple repetition*
print(t1 * 3)          *# (1, 2, 1, 2, 1, 2)# Accessing elements by index*
print(t[0])            *# 1# Slicing*
print(t[1:3])          *# (2, 3)*
```