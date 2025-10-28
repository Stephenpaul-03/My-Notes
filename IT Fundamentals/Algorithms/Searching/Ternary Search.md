## **Definition**

- **Ternary Search** is a **divide-and-conquer** algorithm that cutting the array into **three parts**.
- Used mostly to **find the maximum or minimum** of a **unimodal function** (i.e., a function that increases, peaks, then decreases).

| Best Case | Average Case | Worst Case  | Space Complexity |
| --------- | ------------ | ----------- | ---------------- |
| $O(1)$    | $O(log_3n)$  | $O(log_3n)$ | $O(1)$           |
## **Working**

searching in a **sorted array** between `low` and `high`.

```python
mid1 = low + (high - low) // 3
mid2 = high - (high - low) // 3
```

- If `target == arr[mid1]` → found it
- If `target == arr[mid2]` → found it
- If `target < arr[mid1]` → search the **left third**
- If `target > arr[mid2]` → search the **right third**
- Else → search the **middle third**
## **Code**

```python
def ternary_search(arr, target):
    low = 0
    high = len(arr) - 1

    while low <= high:
        third = (high - low) // 3
        mid1 = low + third
        mid2 = high - third

        if arr[mid1] == target:
            return mid1
        if arr[mid2] == target:
            return mid2

        if target < arr[mid1]:
            high = mid1 - 1
        elif target > arr[mid2]:
            low = mid2 + 1
        else:
            low = mid1 + 1
            high = mid2 - 1

    return -1  # not found

```
