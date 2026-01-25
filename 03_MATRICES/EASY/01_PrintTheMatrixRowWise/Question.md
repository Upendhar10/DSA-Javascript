## Problem Title

### Print Matrix Elements Row Wise

---

## Problem Description

You are given a 2D matrix. Your task is to **print all elements row by row**, starting from the first row to the last row, and from left to right within each row.

### ⚠️ Edge Cases to Consider

* Empty matrix
* Matrix with one row
* Matrix with one column
* Matrix with a single element

---

## Input Format

* A 2D integer matrix `matrix` of size `rows x cols`

---

## Output Format

* Print all elements **row wise** in a single line or multiple lines as per requirement

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
1 2 3 4

Explanation:
Elements are printed row by row from top to bottom.
```

### Example 2

```
Input:
matrix = [[5, 6, 7]]

Output:
5 6 7

Explanation:
Matrix has only one row.
```

### Example 3

```
Input:
matrix = []

Output:
(no output)

Explanation:
Empty matrix has no elements to print.
```

---

## 📏 Constraints

* `0 ≤ rows, cols ≤ 100`
* `-10⁹ ≤ matrix[i][j] ≤ 10⁹`

---

## 📝 Notes ( if any )

* Traversal order matters
* Time Complexity: **O(rows × cols)**

---