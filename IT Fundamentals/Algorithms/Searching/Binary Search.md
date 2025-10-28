## **Definition**

- **Binary Search** is a super efficient algorithm used to find the position of a target in a **sorted array**.
- It cuts the search space in **half** every time.
- Instead of checking every element, it checks the **middle**, and based on that, it decides which half to explore next.

| Best Case | Worst Case | Avg Case   | Space Complexity |
| --------- | ---------- | ---------- | ---------------- |
| $O(1)$    | $O(log~n)$ | $O(log~n)$ | $O(1)$           |
## **Working**

```
arr = [1, 3, 5, 7, 9, 11]
target = 7
```

**Steps**

1. **Start**: low = 0, high = 5
2. **Middle**: mid = (0 + 5) // 2 = 2 → arr[2] = 5
    - Is 5 < 7? Yup → target must be on the **right**
3. Now: low = 3, high = 5 → mid = 4 → arr[4] = 9
    - 9 > 7 → target must be on the **left**
4. Now: low = 3, high = 3 → mid = 3 → arr[3] = 7
    - Found

Index = 3 
## **Code**

```python
#Iterative 

def binary_search(arr, target):
    low = 0
    high = len(arr) - 1

    while low <= high:
        mid = (low + high) // 2

        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            low = mid + 1
        else:
            high = mid - 1

    return -1  # target not found
    
#Recursive

def binary_search_recursive(arr, target, low, high):
    if low > high:
        return -1

    mid = (low + high) // 2

    if arr[mid] == target:
        return mid
    elif arr[mid] < target:
        return binary_search_recursive(arr, target, mid + 1, high)
    else:
        return binary_search_recursive(arr, target, low, mid - 1)

```