## **Introduction**

A **List** in Python is an ordered, mutable, and iterable collection that can store elements of different data types. Lists are dynamic, meaning you can add or remove elements anytime.

## **Working Internally**

- Stored as a dynamic array internally (contiguous memory).
- Allows indexing, slicing, and iteration.
- Maintains insertion order.
- Mutable: elements can be modified.

## **Complexities of Common Operations**

| Operation | Average Time Complexity |
| --- | --- |
| Access by Index | O(1) (constant time) |
| Append | O(1) amortized (may resize) |
| Insert (middle) | O(n) (shifts elements) |
| Remove by Value | O(n) (search + remove) |
| Search (contains) | O(n) (linear search) |
| Pop (end) | O(1) |
| Pop (index) | O(n) (shift elements) |
| Sort | O(n log n) |
| Reverse | O(n) |
| Copy | O(n) |
| Extend | O(k) (where k is iterable size) |

## **Common List Methods**

| Method | Syntax | Usage | Example |
| --- | --- | --- | --- |
| `append()` | `list.append(item)` | Adds an item to the end | `nums.append(5)` |
| `insert()` | `list.insert(index, item)` | Inserts item at given index | `nums.insert(2, 10)` |
| `remove()` | `list.remove(item)` | Removes first occurrence of item | `nums.remove(10)` |
| `pop()` | `list.pop([index])` | Removes and returns element (default last) | `nums.pop()` |
| `sort()` | `list.sort()` | Sorts list in ascending order | `nums.sort()` |
| `reverse()` | `list.reverse()` | Reverses the list | `nums.reverse()` |
| `index()` | `list.index(item)` | Returns index of first occurrence | `nums.index(5)` |
| `count()` | `list.count(item)` | Counts occurrences of item | `nums.count(5)` |
| `extend()` | `list.extend(iterable)` | Extends list by appending elements from iterable | `nums.extend([6,7])` |
| `clear()` | `list.clear()` | Removes all items | `nums.clear()` |
| `copy()` | `list.copy()` | Returns a shallow copy | `new_list = nums.copy()` |
| `del` | `del list[index]` | Deletes item at provided index | `del nums[2]` |

## **Important Notes**

- Lists can contain heterogeneous data types in the same list.
- Lists are dynamic arrays; they automatically resize when elements are added beyond current capacity.
- Insertions/removals at the end are efficient, but in the middle or beginning require shifting elements.
- Iterating through lists takes O(n) time; Python optimizes lookups with indexing (O(1)).
- Lists provide extensive methods for flexible operations and manipulation.

## **List Usage Examples**

```python
nums = [1, 2, 3]
nums.append(4)          *# [1, 2, 3, 4]*
nums.insert(1, 10)      *# [1, 10, 2, 3, 4]*
nums.remove(10)         *# [1, 2, 3, 4]*
nums.pop()              *# [1, 2, 3]*
nums.extend([4, 5])     *# [1, 2, 3, 4, 5]*
nums.sort()             *# [1, 2, 3, 4, 5]*
nums.reverse()          *# [5, 4, 3, 2, 1]*

print(nums.index(3))    *# 2*
print(nums.count(4))    *# 1*

nums.clear()            *# []*
```

## **Copying Lists**

- Use `copy()` method or slicing `[:]` for shallow copies.
- Deep copies (copies nested objects) require `copy` module's `deepcopy()` function.