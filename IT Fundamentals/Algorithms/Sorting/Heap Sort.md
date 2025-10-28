## **Definition**

- Heap Sort is a **comparison-based sorting algorithm** that uses a special tree-based structure called a **Heap** -  specifically, a **Binary Heap**.
- There are two types:
	- **Max Heap**: Parent is always bigger than the children.
	- **Min Heap**: Parent is always smaller than the children.
- Heap Sort usually uses a **Max Heap** because we want the **largest item at the root**, then we remove it and repeat.

| Best/Average/Worst Case            | Space Complexity |
| ---------------------------------- | ---------------- |
| Building Heap + Heapify = Total    |                  |
| $O(N)$ + $O(log~N)$ = $O(N~log~n)$ | $O(1)$           |
## **Conceptual Working**

1. **Build a Max Heap** from the array.
2. **Swap the root (biggest element)** with the last element of the heap.
3. Shrink the heap size (because the last element is now in its final place).
4. **Heapify** the root again.
5. Repeat steps 2-4 until the heap is size 1.

## **Working**

```
[4, 10, 3, 5, 1]
```

## **# Step 1: Build a Max Heap**

```
Visualize the array as a binary tree:
        4
      /   \
    10     3
   /  \
  5    1

Turn it into a Max Heap:

       10
      /   \
    5      3
   /  \
  4    1

Array now:

[10, 5, 3, 4, 1]
```

## **# Step 2: Swap max (10) with last element (1)**

```
[1, 5, 3, 4, 10]

Heapify the root (index 0) → push 1 down the tree:

       5
      / \
    4   3
   /
  1

Array:

[5, 4, 3, 1, 10]
```

## **# Step 3: Swap max (5) with end of heap (1)**

```
[1, 4, 3, 5, 10]

Heapify:

       4
      / \
    1   3

Array:

[4, 1, 3, 5, 10]
```

## **# Step 4: Swap max (4) with 3**

```
[3, 1, 4, 5, 10]

Heapify:

     3
    /
  1

Array:

[3, 1, 4, 5, 10]
```

## **# Step 5: Swap 3 with 1**

```
[1, 3, 4, 5, 10]

```
