## Problem Statement

### Move All Zeros to the End of the Array

---

## Description

Given an array of integers, move **all occurrences of `0` to the end of the array** while maintaining the **relative order of the non-zero elements**.

The operation should be performed **in-place**, without using an additional array for storage.

The relative order of the zeros after the operation does not matter, but the order of non-zero elements **must remain unchanged**.

### Edge Cases to Consider:

* An **empty array** remains unchanged.
* An array with **only one element** remains unchanged.
* An array containing **no zeros** should remain unchanged.
* An array containing **only zeros** should remain unchanged.
* Zeros may appear at the **beginning, middle, or end** of the array.
* The array may contain **negative numbers**.
* Duplicate non-zero values should preserve their original order.

---

## Examples

### Example 1

```
Input:[0, 1, 0, 3, 12]

Output: [1, 3, 12, 0, 0]

Explanation:
    All non-zero elements maintain their relative order, and all zeros are moved to the end.
```

### Example 2

```
Input: [1, 2, 3, 4]

Output: [1, 2, 3, 4]

Explanation:
    There are no zeros in the array, so no changes are needed.
```

### Example 3

```
Input: [0, 0, 0]

Output: [0, 0, 0]

Explanation:
    The array contains only zeros, so it remains unchanged.
```

### Example 4

```
Input: []

Output: []

Explanation:
    An empty array has no elements to process.
```

### Example 5

```
Input: [0]

Output: [0]

Explanation:
    A single-element array containing zero remains unchanged.
```

### Example 6

```
Input: [-1, 0, 2, 0, -3, 4]

Output: [-1, 2, -3, 4, 0, 0]

Explanation:
    Non-zero elements (including negatives) retain their relative order, and zeros are shifted to the end.
```

---

## Constraints

* `0 ≤ N ≤ 10⁵` (where `N` is the number of elements in the array)
* `-10⁹ ≤ array[i] ≤ 10⁹`
* The array contains only integers
* The operation must be performed **in-place**
* Expected time complexity: **O(N)**
* Expected extra space complexity: **O(1)**