## **Definition**

- **Jump Search** is a searching algorithm for **sorted arrays** that **jumps** ahead by fixed steps (**√n)**(blocks), and once it passes the target, it **backtracks** linearly within that block.

| Best Case | Average Case | Worst Case   | Space Complexity |
| --------- | ------------ | ------------ | ---------------- |
| $O(1)$    | $O(\sqrt n)$ | $O(\sqrt n)$ | $O(1)$           |
## **Working**

```
arr = [1, 3, 5, 7, 9, 11, 13, 15, 17, 19]
target = 15
```

Array size = 10 → jump size = √10 ≈ **3**

- Check index 0 → 1 ⇒ Not found and too low
- Check index 3 → 7 ⇒ Not Found and too low
- Check index 6 → 13 ⇒ Not Found and low
- Checked index 9 → 19 ⇒ Not Found and high

Linearly Searches between index 6 to index 9
## **Code**

```python
import math

def jump_search(arr, target):
    n = len(arr)
    step = int(math.sqrt(n))
    prev = 0

    # Jump ahead in blocks
    while prev < n and arr[min(step, n) - 1] < target:
        prev = step
        step += int(math.sqrt(n))
        if prev >= n:
            return -1

    # Linear search in the current block
    for i in range(prev, min(step, n)):
        if arr[i] == target:
            return i

    return -1  # Not found

```
