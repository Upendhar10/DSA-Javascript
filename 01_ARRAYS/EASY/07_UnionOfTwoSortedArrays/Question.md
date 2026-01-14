
## Problem Statement

### Find the Union of Two Sorted Arrays

---

## Description

Given two **sorted arrays** of integers, find the **union** of the two arrays.

The **union** of two arrays is defined as a collection of **distinct elements** that are present in **either one or both** of the arrays.
The resulting array should:

* Contain **only unique elements**
* Be **sorted in non-decreasing order**
* Preserve correctness without using unnecessary extra space where possible

### Edge Cases to Consider:

* If **both arrays are empty**, the union is an empty array.
* If **one array is empty**, the union consists of the elements of the non-empty array (without duplicates).
* Arrays may contain **duplicate elements within themselves**.
* Arrays may share **common elements**.
* Arrays may contain **negative numbers**.
* Arrays may contain **all elements identical**.
* The arrays are guaranteed to be **sorted**.

---

## Examples

### Example 1

```
Input:
Array A: [1, 2, 3, 4, 5]
Array B: [2, 3, 6, 7]

Output: [1, 2, 3, 4, 5, 6, 7]

Explanation:
    All unique elements from both arrays are combined and arranged in sorted order.
```

### Example 2

```
Input:
Array A: [1, 1, 2, 2, 3]
Array B: [2, 2, 3, 4]

Output: [1, 2, 3, 4]

Explanation:
    Duplicate elements within and across arrays are included only once.
```

### Example 3

```
Input:
Array A: []
Array B: [1, 2, 3]

Output: [1, 2, 3]

Explanation:
    One array is empty, so the union is formed from the other array.
```

### Example 4

```
Input:
Array A: []
Array B: []

Output: []

Explanation:
    Both arrays are empty; hence, the union is empty.
```

### Example 5

```
Input:
Array A: [-5, -3, -1, 0]
Array B: [-3, 0, 2, 4]

Output: [-5, -3, -1, 0, 2, 4]

Explanation:
    The union includes all distinct elements from both arrays, including negative numbers.
```
---

## Constraints

* `0 ≤ N, M ≤ 10⁵`
  (where `N` and `M` are the number of elements in Array A and Array B respectively)
* `-10⁹ ≤ array[i] ≤ 10⁹`
* Both arrays are sorted in **non-decreasing order**
* The output should be sorted and contain **only unique elements**
* Expected time complexity: **O(N + M)**
* Expected extra space complexity: **O(N + M)**
  *(Can be optimized depending on approach)*

