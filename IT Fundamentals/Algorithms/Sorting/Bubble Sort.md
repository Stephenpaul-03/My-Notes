## **Definition**

- Bubble Sort is a super simple way to sort a list of numbers.
- It works by **repeatedly swapping** the adjacent elements if they’re in the wrong order.
- Imagine you’re bubbling up the largest number to the end of the list - **like bubbles rising to the surface**, hence the name.

| Best Case | Average Case | Worst Case | Space Complexity |
| --------- | ------------ | ---------- | ---------------- |
| $O(N)$    | $O(N^2)$     | $O(N^2)$   | $O(1)$           |
## **# Working**

```python
[5, 1, 4, 2, 8]
```

## **# First Pass:**

- Compare 5 and 1 → swap → `[1, 5, 4, 2, 8]`
- Compare 5 and 4 → swap → `[1, 4, 5, 2, 8]`
- Compare 5 and 2 → swap → `[1, 4, 2, 5, 8]`
- Compare 5 and 8 → no swap → `[1, 4, 2, 5, 8]`

**Biggest number (8)** has now "bubbled up" to the end.

## **# Second Pass:**

- Compare 1 and 4 → no action → `[1, 4, 2, 5, 8]`
- Compare 4 and 2 → swap → `[1, 2, 4, 5, 8]`
- Compare 4 and 5 → no action → `[1, 2, 4, 5, 8]`
- Compare 5 and 8 → no action → `[1, 2, 4, 5, 8]`
## **# Code**

```python
def bubble_sort(arr):
    n = len(arr)
    for i in range(n):
        # After each pass, the largest element is in place, so we go n - i - 1
        for j in range(0, n-i-1):
            if arr[j] > arr[j+1]:
                # swap
                arr[j], arr[j+1] = arr[j+1], arr[j]

```