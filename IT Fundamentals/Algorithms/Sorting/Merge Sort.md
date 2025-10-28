## **Definition**

- Merge Sort is a **Divide and Conquer** algorithm.
- It breaks the problem into smaller chunks, solves them independently, and then merges the results.

| Best Case    | Average Case | Worst Case   | Space Complexity |
| ------------ | ------------ | ------------ | ---------------- |
| $O(n~log~n)$ | $O(n~log~n)$ | $O(n~log~n)$ | $O(n)$           |
## **Example**

```python
[8, 4, 5, 2, 9, 1]
```

## **# Step 1: Divide**

- [8, 4, 5] and [2, 9, 1]
- Then → [8], [4, 5] and [2], [9, 1]
- Then → [8], [4], [5], [2], [9], [1]

## **# Step 2: Merge**

- Merge [4] and [5] → [4, 5]
- Merge [9] and [1] → [1, 9]
- Merge [8] and [4, 5] → [4, 5, 8]
- Merge [2] and [1, 9] → [1, 2, 9]
- Merge [4, 5, 8] and [1, 2, 9] → `[1, 2, 4, 5, 8, 9]`

## **# Code**

```python
def merge_sort(arr):
    if len(arr) > 1:
        mid = len(arr) // 2
        left = arr[:mid]
        right = arr[mid:]

        # Sort the halves
        merge_sort(left)
        merge_sort(right)

        # Merge the halves
        i = j = k = 0

        while i < len(left) and j < len(right):
            if left[i] < right[j]:
                arr[k] = left[i]
                i += 1
            else:
                arr[k] = right[j]
                j += 1
            k += 1

        # Catch any leftovers
        while i < len(left):
            arr[k] = left[i]
            i += 1
            k += 1
        while j < len(right):
            arr[k] = right[j]
            j += 1
            k += 1

```