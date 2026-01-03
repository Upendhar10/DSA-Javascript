
## Problem Statement

### Check if an Array is Sorted

## Description

Given an array of integers, determine whether the array is **sorted in non-decreasing order** (i.e., each element is **greater than or equal to** the previous element).

An array is considered **sorted** if:

* Every element is **less than or equal to** the next element.
* Duplicate elements are allowed.

### Edge Cases to Consider:

* An **empty array** is considered sorted.
* An array with **only one element** is considered sorted.
* Arrays containing **negative numbers** should be handled correctly.
* Arrays with **duplicate values** should still be considered sorted if order is maintained.
* Arrays that are **strictly decreasing** or have even **one pair out of order** are considered **not sorted**.

The function should return:

* `true` if the array is sorted
* `false` otherwise

## 3. Examples

### Example 1

```
Input: [1, 2, 3, 4, 5]

Output: true

Explanation:
    Each element is less than or equal to the next element, so the array is sorted.
```

### Example 2
```
Input: [1, 2, 2, 3, 4]

Output: true

Explanation:
    Duplicate values are allowed. The order is non-decreasing.
```

### Example 3
```
Input: [5, 4, 3, 2, 1]

Output: false

Explanation:
    The array is strictly decreasing, so it is not sorted in non-decreasing order.
```

### Example 4
```
Input: [1, 3, 2, 4]

Output: false

Explanation: 
    The element `3` is greater than `2`, which breaks the sorted order.
```

### Example 5
```
Input: []

Output: true

Explanation: 
    An empty array has no elements to violate the sorted condition.

``` 

### Example 6

```
Input: [7]

Output: true

Explanation:
    A single-element array is always considered sorted.

```

### Example 7

```
Input: [-5, -3, -1, 0, 2]

Output: true

Explanation: 
    The array contains negative numbers but still follows a non-decreasing order.
```

## 4. Constraints

* `0 ≤ N ≤ 10⁵` (where `N` is the number of elements in the array)
* `-10⁹ ≤ array[i] ≤ 10⁹`
* The array contains only integers.
* The solution should ideally run in **O(N)** time complexity.
* No modification to the original array is required.

---

