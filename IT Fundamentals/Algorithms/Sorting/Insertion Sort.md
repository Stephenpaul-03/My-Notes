## **Definition**

- Insertion Sort builds the sorted list **one item at a time.**

| Best Case | Average Case | Worst Case | Space Complexity |
| --------- | ------------ | ---------- | ---------------- |
| $O(N)$    | $O(N^2)$     | $O(N^2)$   | $O(1)$           |
## **Working**

```python
[8, 4, 1, 3, 5]
```

Start from index 1
- **i = 1, key = 4**
    Compare with 8 → shift 8 right → insert 4 → `[4, 8, 1, 3, 5]`
- **i = 2, key = 1**
    Compare with 8, 4 → shift both → insert 1 → `[1, 4, 8, 3, 5]`
- **i = 3, key = 3**
    Compare with 8, 4 → shift both → insert 3 → `[1, 3, 4, 8, 5]`
- **i = 4, key = 5**
    Compare with 8 → shift 8 → insert 5 → `[1, 3, 4, 5, 8]`
    
## **Code**

```python
def insertion_sort(arr):
    for i in range(1, len(arr)):
        key = arr[i]
        j = i - 1
        while j >= 0 and key < arr[j]:
            arr[j + 1] = arr[j]  # shift right
            j -= 1
        arr[j + 1] = key
```
