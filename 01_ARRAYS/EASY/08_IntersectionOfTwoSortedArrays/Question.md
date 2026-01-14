
## Problem Title

### Find the Intersection of Two Sorted Arrays

---

## Description

Given two **sorted arrays** of integers, find the **intersection** of the two arrays.

The **intersection** of two arrays is defined as a collection of **distinct elements** that are present in **both** arrays.

The resulting array should:

* Contain **only unique elements**
* Be **sorted in non-decreasing order**

The operation should be performed efficiently by leveraging the fact that the input arrays are already sorted.

### Edge Cases to Consider:

* If **either array is empty**, the intersection is an empty array.
* If **both arrays are empty**, the intersection is an empty array.
* Arrays may contain **duplicate elements within themselves**.
* Arrays may contain **no common elements**.
* Arrays may contain **all elements common**.
* Arrays may contain **negative numbers**.
* The arrays are guaranteed to be **sorted**.

---

## Examples

### Example 1

```
Input :
Array A: [1, 2, 3, 4, 5]
Array B: [2, 3, 6, 7]

Output: [2, 3]

Explanation:
    Only elements that appear in both arrays are included.
```

### Example 2

```
Input :
Array A: [1, 1, 2, 2, 3]
Array B: [2, 2, 3, 4]

Output: [2, 3]

Explanation:
    Duplicate elements are included only once in the result.
```
---

### Example 3

```
Input :
Array A: []
Array B: [1, 2, 3]

Output: []

Explanation:
    One array is empty, so no common elements exist.
```

### Example 4

```
Input : 
Array A: []
Array B: []

Output: []

Explanation:
    Both arrays are empty, so the intersection is empty.
```
---

### Example 5

```
Input : 
Array A: [-5, -3, -1, 0]
Array B: [-3, 0, 2, 4]

Output: [-3, 0]

Explanation:
    Only the elements common to both arrays are included.
```

---

## 4. Constraints

* `0 ≤ N, M ≤ 10⁵`
  (where `N` and `M` are the number of elements in Array A and Array B)
* `-10⁹ ≤ array[i] ≤ 10⁹`
* Both arrays are sorted in **non-decreasing order**
* The result must contain **only unique elements**
* Expected time complexity: **O(N + M)**
* Expected extra space complexity: **O(min(N, M))**
  *(or O(1) if output space is not counted)*

