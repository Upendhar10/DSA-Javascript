
## Problem Statement

### Find the Number That Appears Once

---

## Problem Description

You are given an integer array where **every element appears exactly twice except for one element**, which appears **only once**.

Your task is to **identify and return the element that appears exactly one time**.

The array is **not necessarily sorted**, and the unique element can appear at **any position** in the array.

### Edge Cases to Consider

* Array of length `1`
* Unique element at the:

  * Beginning
  * Middle
  * End of the array
* Array containing:

  * Negative numbers
  * Zero
* Very large array size

---

## Input Format

* An integer array `arr` of length `n`
* All elements appear exactly twice **except one**

---

## Output Format

* Return the integer value that appears **only once**

---

## Examples

### Example 1

```
Input: arr = [2, 2, 1]
Output: 1
Explanation:
* `2` appears twice
* `1` appears once
* Hence, the answer is 1
```

### Example 2

```
Input: arr = [4, 1, 2, 1, 2]
Output: 4
Explanation:
* `1` and `2` appear twice
* `4` appears only once
* The unique number is **4**
```

### Example 3
```
Input: arr = [7]
Output: 7
Explanation:
* Single element in the array
* It appears once by definition
```

### Example 4
```
Input: arr = [0, -1, 0]
Output: -1
Explanation:
* `0` appears twice
* `-1` appears once
* The unique element is **-1**
```

### Example 5 (Unordered Array)
```
Input: arr = [10, 5, 10, 3, 5]
Output:3
Explanation:
* All numbers except `3` occur twice
* Order does not affect the result
```

---

## Constraints

* `1 ≤ n ≤ 10⁵`
* `n` is **odd**
* `-10⁹ ≤ arr[i] ≤ 10⁹`
* Exactly **one element appears once**
* All other elements appear **exactly twice**

---

## Notes

* There will always be **exactly one unique element**
* The solution is expected to be efficient

* This problem is commonly used to test:
  * Bitwise reasoning
  * Hashing vs constant-space optimization

* An optimal solution exists with:
  * **O(n)** time complexity
  * **O(1)** extra space