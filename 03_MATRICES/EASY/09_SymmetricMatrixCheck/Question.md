## Problem Title

### Check Whether a Matrix is Symmetric

---

## Problem Description

A matrix is **symmetric** if it is equal to its transpose.
Determine whether the given matrix is symmetric.

### ⚠️ Edge Cases to Consider

* Empty matrix
* 1×1 matrix
* Non-square matrix

---

## Input Format

* A matrix `matrix`

---

## Output Format

* Return `true` if symmetric, otherwise `false`

---

## Examples

### Example 1

```
Input:
matrix = [
  [1, 2],
  [2, 1]
]

Output:
true

Explanation:
Matrix equals its transpose.
```

### Example 2

```
Input:
matrix = [
  [1, 2, 3],
  [4, 5, 6]
]

Output:
false

Explanation:
Non-square matrix cannot be symmetric.
```

---

## 📏 Constraints

* `0 ≤ rows, cols ≤ 100`

---

## 📝 Notes ( if any )

* Only square matrices can be symmetric

---
