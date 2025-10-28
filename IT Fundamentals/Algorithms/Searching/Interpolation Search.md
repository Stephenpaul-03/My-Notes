## **Definition**

- **Interpolation Search** is a **search algorithm for sorted, uniformly distributed arrays**.
- It improves over Binary Search by estimating where the value might be.

| Best Case | Average Case   | Worst Case | Space Complexity |
| --------- | -------------- | ---------- | ---------------- |
| $O(1)$    | $O(log~log~n)$ | $O(n)$     | $O(1)$           |
## **Formula**

```python
pos = low + ((target - arr[low]) * (high - low)) // (arr[high] - arr[low])
```
## **Working**

Apply the formula based on the value from the array to find the target.

```
arr = [10, 20, 30, 40, 50, 60, 70]
target = 50
low = 0
high = 6
pos = low + ((target - arr[low]) * (high - low)) // (arr[high] - arr[low])
pos = 0 + ((50 - 10) * (6 - 0)) // (70 - 10)
    = (40 * 6) // 60 = 240 // 60 = 4

```
## **Code**

```python
def interpolation_search(arr, target):
    low = 0
    high = len(arr) - 1

    while low <= high and arr[low] <= target <= arr[high]:
        # Prevent division by zero
        if arr[high] == arr[low]:
            if arr[low] == target:
                return low
            else:
                return -1

        # Estimate position
        pos = low + ((target - arr[low]) * (high - low)) // (arr[high] - arr[low])

        if arr[pos] == target:
            return pos
        elif arr[pos] < target:
            low = pos + 1
        else:
            high = pos - 1

    return -1  # Not found

```