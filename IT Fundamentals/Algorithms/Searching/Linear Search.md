## **Definition**

- Linear Search goes **element by element** through a list and checks if the current item is what you're looking for.
- Also known as Sequential Search

| Best Case | Average case | Worst Case | Space Complexity |
| --------- | ------------ | ---------- | ---------------- |
| $O(1)$    | $O(n)$       | $O(n)$     | $O(1)$           |

## **Working**

if x = 5, 

```
[3, 1, 4, 5, 9]
```

Steps:

1. Is 3 == 5? False
2. Is 1 == 5? False
3. Is 4 == 5? False
4. Is 5 == 5? True → FOUND at index 3
## **Code**

```python
def linear_search(arr, target):
    for i in range(len(arr)):
        if arr[i] == target:
            return i  # return the index
    return -1  # not found

```
