
## Problem Statement :

### Left Rotate an Array by K Positions

---

## Description

Given an array of integers and a non-negative integer `K`, rotate the array **to the left by `K` positions**.

In a left rotation:

* Elements shifted beyond the first index **wrap around to the end** of the array.
* The relative order of the remaining elements is preserved.
* The rotation is **cyclic** in nature.

If `K` is greater than the length of the array, the effective number of rotations should be adjusted accordingly.

The rotation should be performed **in-place**, without using an additional array.

### Edge Cases to Consider:

* An **empty array** remains unchanged.
* An array with **only one element** remains unchanged, regardless of `K`.
* If `K = 0`, the array remains unchanged.
* If `K` is a **multiple of the array length**, the array remains unchanged.
* Arrays may contain **negative numbers**.
* Arrays may contain **duplicate values**.
* When `K = 1`, this operation is equivalent to **cyclically rotating the array left by one position**.

---

## Examples

### Example 1

```
Input: Array: [1, 2, 3, 4, 5] , K = 1

Output: [2, 3, 4, 5, 1]

Explanation:
    Rotating the array left by 1 moves the first element to the end.
```

### Example 2

```
Input: Array: [1, 2, 3, 4, 5] , K = 2

Output: [3, 4, 5, 1, 2]

Explanation:
    The array is rotated left by 2 positions.
```


### Example 3

```
Input: Array: [10, 20, 30, 40] , K = 4

Output: [10, 20, 30, 40]

Explanation: Since `K` equals the array length, the array remains unchanged.
```

### Example 4

```
Input: Array: [7] , K = 3

Output: [7]

Explanation:
    A single-element array remains unchanged after any number of left rotations.
```

### Example 5

```
Input: Array: [] , K = 5

Output: []

Explanation:
    An empty array has no elements to rotate.
```

### Example 6

```
Input: Array: [-1, -2, -3, -4] , K = 1

Output: [-2, -3, -4, -1]

Explanation:
    Left rotation works correctly even with negative numbers.
```
---

## 4. Constraints

* `0 ≤ N ≤ 10⁵` (where `N` is the number of elements in the array)
* `0 ≤ K ≤ 10⁹`
* `-10⁹ ≤ array[i] ≤ 10⁹`
* The array contains only integers
* The rotation must be performed **in-place**
* Expected time complexity: **O(N)**
* Expected extra space: **O(1)**

---

### Insights 🧠

Left rotation and right rotation are **mirror problems**:

* Left rotate by `K` ⟺ Right rotate by `N − K`
* Understanding one makes the other trivial
