
## Problem Statement

### Remove Duplicates from a Sorted Array

---

## Description

Given a **sorted array of integers**, remove the duplicate elements **in-place** such that each unique element appears **only once** and the **relative order** of the elements is preserved.

After removing duplicates:

* The first `K` elements of the array should contain the **unique elements** in sorted order.
* The function should return the value of `K`, representing the **count of unique elements**.
* The elements beyond index `K - 1` do not matter.

### Edge Cases to Consider:

* An **empty array** should return `0`.
* An array with **only one element** should return `1`.
* An array where **all elements are the same** should return `1`.
* An array with **no duplicate elements** should remain unchanged.
* Arrays may contain **negative numbers**.
* The input array is **guaranteed to be sorted**, either in increasing order or with equal adjacent values.

⚠️ No additional array or data structure should be used for storing unique elements.

---

## 3. Examples

### Example 1

```
Input: [1, 1, 2]

Output: K = 2  

Modified array (first K elements): [1, 2]

Explanation:
    The duplicates of `1` are removed. The unique elements are `1` and `2`.
```

### Example 2

```
Input: [0, 0, 1, 1, 1, 2, 2, 3, 3, 4]

Output: K = 5  

Modified array (first K elements): [0, 1, 2, 3, 4]

Explanation:
    Each number appears only once in the first `K` positions of the array.

```

### Example 3

```
Input: []

Output: K = 0

Explanation:
    The array is empty, so there are no unique elements.

```

### Example 4

```
Input: [5]

Output: K = 1  

Modified array (first K elements): [5]

Explanation:
    A single-element array always contains exactly one unique value.

```

### Example 5

```
Input: [2, 2, 2, 2, 2]

Output: K = 1  

Modified array (first K elements): [2]

Explanation:
    All elements are duplicates, so only one unique element remains.

```

### Example 6
```
Input: [-3, -3, -1, 0, 0, 2, 2]

Output: K = 4  

Modified array (first K elements): [-3, -1, 0, 2]

Explanation:
    Duplicates are removed while preserving sorted order, including negative numbers.
```

## 4. Constraints

* `0 ≤ N ≤ 10⁵` (where `N` is the number of elements in the array)
* `-10⁹ ≤ array[i] ≤ 10⁹`
* The array is **sorted in non-decreasing order**
* The operation must be performed **in-place**
* **O(1)** extra space is allowed
* Expected time complexity: **O(N)**

---
