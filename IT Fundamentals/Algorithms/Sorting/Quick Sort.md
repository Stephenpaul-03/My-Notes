## **Definition**

- Quick Sort is **Divide and Conquer** algorithm,
- Quick Sort **picks a “pivot”** and then **reorganizes** the array so that:
- Elements smaller than the pivot go left
- Elements bigger go right
- Then it **recursively sorts** the left and right sides.

| Best Case    | Average Case | Worst Case | Space Complexity |
| ------------ | ------------ | ---------- | ---------------- |
| $O(n~log~n)$ | $O(n~log~n)$ | $O(n^2)$   | $O(log~n)$       |
## **Example**

```
[9, 3, 7, 1, 5]
```

## **# **Pivot is the First Element****

**Step 1: Partition around pivot 9**

- Everything less than 9: `[3, 7, 1, 5]`
- Nothing is greater (all < 9 except 9)

**Step 2: Recurse on `[3, 7, 1, 5]` with pivot = 3**

- Less than 3: `[1]`
- Greater: `[7, 5]`

**Step 3: Recurse on `[7, 5]` with pivot = 7**

- Less than 7: `[5]`
- Greater: `[]`

```
Step 1 : [3, 7, 1, 5] + [9]
Step 2 : [1] + [3] + [7, 5]
Step 3 : [5] + [7]
Final  : [1] + [3] + [5] + [7] + [9] → [1, 3, 5, 7, 9]
```

## **# **Pivot is the Last Element****

**Step 1: Partition around pivot 5**

- Less than 5: `[3, 1]`
- Greater than 5: `[9, 7]`

Step 2: Recurse on `[3, 1]`, pivot = 1

- Less than 1: `[]`
- Greater than 1: `[3]`

Step 3: Recurse on `[9, 7]`, pivot = 7

- Less than 7: `[]`
- Greater than 7: `[9]`

```
Step 1 : [3, 1] + [5] + [9, 7]
Step 2 : [] + [1] + [3]
Step 3 : [] + [7] + [9]
Final  : [1, 3] + [5] + [7, 9] → [1, 3, 5, 7, 9]
```

## **# **Pivot is the Middle Element****

**Step 1: Partition around 7**

- Less than 7: `[3, 1, 5]`
- Greater: `[9]`

**Step 2: Recurse on `[3, 1, 5]`, pivot = middle = 1**

- Less than 1: `[]`
- Greater: `[3, 5]`

**Step 3: Recurse on `[3, 5]`, pivot = middle = 3**

- Less than 3: `[]`
- Greater: `[5]`

So:

```
Step 1 : [3, 1, 5] + [7] + [9]
Step 2 : [] + [1] + [3, 5]
Step 3 : [] + [3] + [5]
Final  : [1, 3, 5] + [7] + [9] → [1, 3, 5, 7, 9]
```

## **Code**

```python
def quick_sort(arr):
    if len(arr) <= 1:
        return arr
    pivot = arr[len(arr) // 2]  # middle element as pivot
    left = [x for x in arr if x < pivot]
    middle = [x for x in arr if x == pivot]
    right = [x for x in arr if x > pivot]
    return quick_sort(left) + middle + quick_sort(right)

#Or the in-place version (more efficient memory-wise):
def quick_sort_inplace(arr, low, high):
    if low < high:
        pi = partition(arr, low, high)
        quick_sort_inplace(arr, low, pi - 1)
        quick_sort_inplace(arr, pi + 1, high)

def partition(arr, low, high):
    pivot = arr[high]
    i = low - 1
    for j in range(low, high):
        if arr[j] < pivot:
            i += 1
            arr[i], arr[j] = arr[j], arr[i]
    arr[i + 1], arr[high] = arr[high], arr[i + 1]
    return i + 1
```

---