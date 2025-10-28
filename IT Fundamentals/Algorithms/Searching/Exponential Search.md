## **Definition**

- Exponential Search is a **search algorithm for sorted arrays**.
- It works in two phases:
	- **Phase 1: Exponential Jumping**
		- Start at index `1`, then keep **doubling** the index (`1, 2, 4, 8, 16...`) until you find a range where the target could be
	- **Phase 2: Binary Search**
		- Once jumped past or hit the target, binary search kicks in *between the last good index and the overshot*.
	
| Best Case | Average Case | Worst Case | Space Complexity |
| --------- | ------------ | ---------- | ---------------- |
| $O(1)$    | $O(log~i)$   | $O(log~i)$ | $O(1)$           |
## **When to Use**

- **Unbounded sorted arrays** (like if you're searching in an infinite list)
- **Large sorted arrays** where you have no clue where the target might be
- **Fast search times** when the target is near the front
## **Working**

```
[2, 4, 6, 10, 14, 18, 22, 26, 30, 34]
target = 22
```

## **# Phase 1: Exponential Jumping**

- `arr[1] = 4` → too small
- `arr[2] = 6` → still small
- `arr[4] = 14` → getting close
- `arr[8] = 30` → too big

Target is between **index 4 and 8**

## **# Phase 2: Binary Search**

Apply Binary Search between index 4 and index 8 `[14, 18, 22, 26, 30]`
## **Code**

```python
def binary_search(arr, target, low, high):
    while low <= high:
        mid = (low + high) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            low = mid + 1
        else:
            high = mid - 1
    return -1

def exponential_search(arr, target):
    if not arr:
        return -1

    if arr[0] == target:
        return 0

    i = 1
    while i < len(arr) and arr[i] <= target:
        i *= 2

    # Do binary search between i/2 and min(i, len(arr)-1)
    return binary_search(arr, target, i // 2, min(i, len(arr) - 1))

```
