## **Definition**

- Selection Sort sorts a list by **repeatedly finding the smallest (or largest) element** from the **unsorted part** and putting it at the **beginning**.

| Best Case | Average Case | Worst Case | Time Complexity |
| --------- | ------------ | ---------- | --------------- |
| $O(N^2)$  | $O(N^2)$     | $O(N^2)$   | $O(1)$          |
## **Working**

```python
[29, 10, 14, 37, 14]
```

## **# First Pass:**

- Find the smallest: 10
- Swap with the first: `[10, 29, 14, 37, 14]`

## **# Second Pass:**

- From index 1 to end: smallest is 14
- Swap with index 1: `[10, 14, 29, 37, 14]`

## **# Third Pass:**

- From index 2 to end: smallest is 14
- Swap with index 2: `[10, 14, 14, 37, 29]`

## **# Fourth Pass:**

- From index 3 to end: smallest is 29
- Swap with 37: `[10, 14, 14, 29, 37]`
## **Code**

```python
def selection_sort(arr):
    n = len(arr)
    for i in range(n):
        min_index = i
        for j in range(i+1, n):
            if arr[j] < arr[min_index]:
                min_index = j
        # swap the found min with the current i
        arr[i], arr[min_index] = arr[min_index], arr[i]

```
