## **Introduction**

A **Set** in Python is an unordered collection of unique elements. It automatically removes duplicate values and stores only one instance of each item.

## **Working Internally**

- Implemented using a **hash table** similar to dictionaries.
- Elements are hashed to allow fast membership testing, insertion, and removal.
- Sets are unordered collections — indexing and slicing are not supported.
- Sets are **mutable**: you can add or remove elements, but elements themselves must be immutable (e.g., strings, numbers, tuples).
- Supports heterogeneous data types in the same set.

## **Complexities of Common Operations**

| Operation         | Average Time Complexity                 |
| ----------------- | --------------------------------------- |
| Add               | O(1)                                    |
| Remove            | O(1)                                    |
| Discard           | O(1)                                    |
| Search (contains) | O(1)                                    |
| Union             | O(len(s) + len(t))                      |
| Intersection      | O(min(len(s), len(t)))                  |
| Difference        | O(len(s))                               |
| Iteration         | O(n), where n is the number of elements |

*Note:* Worst-case can degrade due to hash collisions but are rare with good hashing.

## **Common Set Methods**

| Method                   | Syntax                      | Usage                                        | Example                     |
| ------------------------ | --------------------------- | -------------------------------------------- | --------------------------- |
| `add()`                  | `set.add(item)`             | Adds an element                              | `s.add(5)`                  |
| `remove()`               | `set.remove(item)`          | Removes item, raises KeyError if missing     | `s.remove(5)`               |
| `discard()`              | `set.discard(item)`         | Removes item if present, no error if missing | `s.discard(10)`             |
| `pop()`                  | `set.pop()`                 | Removes and returns an arbitrary element     | `s.pop()`                   |
| `clear()`                | `set.clear()`               | Removes all elements                         | `s.clear()`                 |
| `union()`                | `set.union(other)`          | Returns union of sets                        | `s.union({6,7})`            |
| `intersection()`         | `set.intersection(other)`   | Returns common elements                      | `s.intersection({2,3})`     |
| `difference()`           | `set.difference(other)`     | Elements in set not in other                 | `s.difference({2,3})`       |
| `issubset()`             | `set.issubset(other)`       | Checks if set is subset of other             | `s.issubset(t)`             |
| `issuperset()`           | `set.issuperset(other)`     | Checks if set is superset of other           | `s.issuperset(t)`           |
| `symmetric_difference()` | `s.symmetric_difference(t)` | Elements in either set but not both          | `s.symmetric_difference(t)` |

## **Set Comprehensions**

- Similar to list comprehensions but produce a set.
- Syntax:
    
    ```python
    {expression for item in iterable if condition}
    ```
    

Example:

```python
usernames = ["Alice", " bob", "ALICE ", "Bob", "charlie", "Charlie", "JOHN"]
clean_usernames = {name.lower().strip() for name in usernames}
*# {'bob', 'alice', 'john', 'charlie'}*
```

## **Important Notes**

- Sets cannot contain mutable elements like lists or other sets as elements.
- Unordered: no guaranteed order and no indexing.
- Addition/removal operations affect set dynamically.
- Useful for membership testing, filtering duplicates, set algebra.

## **Example Usage**

```python
s = {1, 2, 3}
s.add(4)                       *# {1, 2, 3, 4}*
s.remove(4)                    *# {1, 2, 3}*
s.discard(10)                  *# {1, 2, 3}, no error*
print(s.union({4, 5}))         *# {1, 2, 3, 4, 5}*
print(s.intersection({2, 4}))  *# {2}*
print(s.difference({2}))       *# {1, 3}# Set comprehension to clean list of usernames*
usernames = ["Alice", " bob", "ALICE ", "Bob"]
cleaned = {name.lower().strip() for name in usernames}
print(cleaned)  *# {'alice', 'bob'}*
```
