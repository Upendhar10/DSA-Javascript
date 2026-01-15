
## Problem Statement

### Find Maximum Consecutive Ones in an Array

---

## Problem Description

You are given an array consisting of integers `0` and `1` only.
Your task is to determine the **maximum number of consecutive `1`s** present in the array.

Consecutive means the `1`s must appear **continuously without interruption** by `0`.

### What you need to compute

* Identify all segments of continuous `1`s.
* Return the **length of the longest such segment**.

### Edge Cases to Consider

* Empty array
* Array with all `0`s
* Array with all `1`s
* Single element array
* Alternating `0`s and `1`s
* Consecutive `1`s appearing at:
  * Beginning of the array
  * End of the array


## Input Format

* An integer array `arr` of length `n`
* Each element of the array is either `0` or `1`

---

## Output Format

* Return a single integer representing the **maximum count of consecutive `1`s**.

---

## Examples

### Example 1

```
Input: arr = [1, 1, 0, 1, 1, 1]
Output: 3
Explanation:
There are two groups of consecutive `1`s:
  * First group → `[1, 1]` → length = 2
  * Second group → `[1, 1, 1]` → length = 3
Maximum among them is 3.
```

### Example 2

```
Input: arr = [0, 0, 0, 0]
Output: 0
Explanation:
* There are no `1`s in the array.
* Hence, the maximum consecutive `1`s count is 0.
```

### Example 3
```
Input: arr = [1, 1, 1, 1]
Output: 4
Explanation:
* The entire array consists of `1`s.
* All are consecutive, so the result is the array length → 4.
```

### Example 4
```
Input: arr = [1, 0, 1, 0, 1]
Output:1
Explanation:
* Each `1` is isolated.
* The maximum consecutive count is 1.
```

### Example 5 (Edge Case)
```
Input: arr = []
Output: 0
Explanation:
* Empty array contains no elements.
* Hence, the result is **0**.
```

### Example 6 (Single Element)
```
Input: arr = [1]
Output: 1
Explanation:
* Single `1` forms a consecutive sequence of length **1**.
```
---

## 📏 Constraints

* `0 ≤ n ≤ 10⁵`
* `arr[i] ∈ {0, 1}`

---

## 📝 Notes

* The solution should ideally run in **O(n)** time.
* No extra space is required beyond a few variables.
* This problem is commonly used to test:
  * Array traversal
  * Counter reset logic
  * Basic pattern recognition