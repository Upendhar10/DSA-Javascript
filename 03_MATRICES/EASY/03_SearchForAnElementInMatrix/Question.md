## Problem Title

### Search an Element in a Matrix

---

## Problem Description

You are given a matrix and a target value. Determine whether the **target element exists** in the matrix.

### ⚠️ Edge Cases to Consider

* Empty matrix
* Matrix with one element
* Target present multiple times
* Target not present

---

## Input Format

* A 2D integer matrix `matrix`
* An integer `target`

---

## Output Format

* Return `true` if found, otherwise `false`

---

## Examples

### Example 1

```
Input:
matrix = [
  [1, 2],
  [3, 4]
]
target = 3

Output:
true

Explanation:
Target exists in the matrix.
```

### Example 2

```
Input:
matrix = [[5]]
target = 10

Output:
false

Explanation:
Target is not present.
```

### Example 3

```
Input:
matrix = []

Output:
false

Explanation:
Empty matrix cannot contain any element.
```

---

## 📏 Constraints

* `0 ≤ rows, cols ≤ 100`

---

## 📝 Notes ( if any )

* Linear traversal solution expected for easy level

---