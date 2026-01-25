
## Problem Title

### Print Matrix Elements Column Wise

---

## Problem Description

Given a 2D matrix, print its elements **column by column**, starting from the first column to the last column, and from top to bottom within each column.

### ⚠️ Edge Cases to Consider

* Empty matrix
* Matrix with one row
* Matrix with one column
* Single element matrix

---

## Input Format

* A 2D integer matrix `matrix`

---

## Output Format

* Print all elements **column wise**

---

## Examples

### Example 1

```
Input:
matrix = [
  [1, 2],
  [3, 4]
]

Output:
1 3 2 4

Explanation:
First column printed first, then second column.
```

### Example 2

```
Input:
matrix = [[8], [9], [10]]

Output:
8 9 10

Explanation:
Only one column exists.
```

### Example 3

```
Input:
matrix = []

Output:
(no output)

Explanation:
Empty matrix.
```

---

## 📏 Constraints

* `0 ≤ rows, cols ≤ 100`

---

## 📝 Notes ( if any )

* Column-first traversal
* Time Complexity: **O(rows × cols)**

---