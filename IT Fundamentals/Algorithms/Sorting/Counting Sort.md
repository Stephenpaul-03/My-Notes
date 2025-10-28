## **Definition**

- **Counting Sort** is an **integer sorting algorithm** used when:
- known range of the input values. (Has to be small)
- **Non-negative integers**
	- Instead of comparing, it **counts** how many times each value appears, then uses that info to build the sorted array.

| Best/Average/Worst Case | Space Complexity |
| ----------------------- | ---------------- |
| $O(n~+~K)$              | $O(K)$           |
## **Conceptual Working**

1. Find the biggest number (let's call it `k`).
2. Create a “count array” of size `k+1` to tally up how many times each number shows up.
3. Uses that tally to put everything in the correct order.
## **Working**

```
[4, 2, 2, 8, 3, 3, 1]
```
## **# Step 1: Find the max value**

Max = `8` , so we make a **count array** of size `9` (from 0 to 8)

## **# Step 2: Count the frequency of each number**

Loop through the input:

- 4 → count[4]++
- 2 → count[2]++
- 2 → count[2]++
- 8 → count[8]++
- 3 → count[3]++
- 3 → count[3]++
- 1 → count[1]++

## **# Step 3: Build the sorted array using the count array**

Walk through `count` and spit out each value `count[i]` times:

- 1 → once
- 2 → twice
- 3 → twice
- 4 → once
- 8 → once

```
Initial Value =   [4, 2, 2, 8, 3, 3, 1]
Step 1 => count = [0, 0, 0, 0, 0, 0, 0, 0, 0]
Step 2 => count = [0, 1, 2, 2, 1, 0, 0, 0, 1]
Step 3 => final = [1, 2, 2, 3, 3, 4, 8]
```

## **Code**

```python
#Basic Count Sort without Duplicate Management

def counting_sort(arr):
    if not arr:
        return []

    max_val = max(arr)
    count = [0] * (max_val + 1)

    # Count each number
    for num in arr:
        count[num] += 1

    # Build the sorted array
    sorted_arr = []
    for num, freq in enumerate(count):
        sorted_arr.extend([num] * freq)

    return sorted_arr

#Count Sort with Duplicate Management and Order Preserving
def stable_counting_sort(arr):
    if not arr:
        return []

    max_val = max(arr)
    count = [0] * (max_val + 1)

    # Count frequencies
    for num in arr:
        count[num] += 1

    # Transform count[i] to hold actual positions
    for i in range(1, len(count)):
        count[i] += count[i - 1]

    output = [0] * len(arr)

    # Build the output array backwards for stability
    for i in reversed(range(len(arr))):
        num = arr[i]
        count[num] -= 1
        output[count[num]] = num

    return output

## **Example usage**
arr = [4, 2, 2, 8, 3, 3, 1]
print(stable_counting_sort(arr))  # Output: [1, 2, 2, 3, 3, 4, 8]

```