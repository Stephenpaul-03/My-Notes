## **Introduction**

A **Dictionary** in Python is an unordered collection of key-value pairs. Keys must be unique and immutable (such as strings, numbers, or tuples). Values can be of any type and are mutable.

## **Working Internally**

- Implemented using a **hash table** for efficient key-based access.
- Keys → immutable (hashable)
- Values → mutable
- Maintains insertion order (Python 3.7+).

## **Complexities of Common Operations**

| Operation | Average Time Complexity |
| --- | --- |
| Access by Key | O(1) (constant time) |
| Insert | O(1) |
| Delete | O(1) |
| Search for Key | O(1) |
| Iteration | O(n) (n = number of items) |
| Get all keys | O(n) |
| Get all values | O(n) |
| Copy | O(n) |
| Clear | O(1) |

*Note:* Worst-case complexities can degrade to O(n) due to hash collisions but are rare with a good hashing function.

## **Common Dictionary Methods**

| Method | Syntax | Description | Example |
| --- | --- | --- | --- |
| `get()` | `dict.get(key)` | Returns value for key, or `None` if not found | `d.get('a')` |
| `keys()` | `dict.keys()` | Returns all keys as a view | `d.keys()` |
| `values()` | `dict.values()` | Returns all values as a view | `d.values()` |
| `items()` | `dict.items()` | Returns key-value pairs as a view | `d.items()` |
| `pop()` | `dict.pop(key)` | Removes specified key and returns its value | `d.pop('a')` |
| `popitem()` | `dict.popitem()` | Removes and returns last inserted key-value | `d.popitem()` |
| `update()` | `dict.update(other)` | Updates dict with another dictionary or iterable | `d.update({'b': 2})` |
| `clear()` | `dict.clear()` | Removes all items | `d.clear()` |
| `copy()` | `dict.copy()` | Returns a shallow copy of the dictionary | `new_d = d.copy()` |
| `setdefault()` | `dict.setdefault(key, default=None)` | Returns value of key or inserts it with default | `d.setdefault('x', 0)` |

## **Additional Important Notes**

- Dictionary views (`keys()`, `values()`, `items()`) reflect changes in the dictionary dynamically.
- Dictionary keys must be hashable (immutable).
- Dictionaries preserve insertion order since Python 3.7+.
- Efficient for fast lookups, insertions, and deletions compared to lists.

## **Example Code**

```python
d = {'a': 1, 'b': 2}
print(d.get('a'))             *# 1*
d.update({'c': 3})            *# {'a':1, 'b':2, 'c':3}*
print(d.keys())               *# dict_keys(['a', 'b', 'c'])*
print(d.values())             *# dict_values([1, 2, 3])*
print(d.items())              *# dict_items([('a',1), ('b',2), ('c',3)])*
d.pop('a')                   *# removes 'a'*
d.popitem()                  *# removes last inserted item*
```