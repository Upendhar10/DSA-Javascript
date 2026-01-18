## Problem Title

### Sort Product Prices in Ascending Order

---

## Problem Description

You are given an array representing the prices of products in an online store.
The prices are **unsorted**, and your task is to **sort the prices in ascending order**.

You must rearrange the elements such that:

* The smallest price comes first
* The largest price comes last

This problem is intentionally designed to be solved using the **Bubble Sort algorithm**, where adjacent elements are repeatedly compared and swapped if they are in the wrong order.

---

## Input Format

* An integer array `prices` of length `n`
* Each element represents the price of a product

---

## Output Format

* Return the array sorted in **ascending order**

---

## Examples

### Example 1 

```
Input:
prices = [450, 120, 300, 200]

Output: [120, 200, 300, 450]

Explanation:

- Adjacent prices are compared and swapped step by step
- Larger prices gradually move toward the end of the array
```

### Example 2

```
Input:
prices = [10, 20, 30, 40]

Output: [10, 20, 30, 40]

Explanation:

- The array is already sorted
- Bubble Sort will detect no swaps
```

### Example 3

```
Input:
prices = [90, 70, 50, 30]

Output: [30, 50, 70, 90]

Explanation:

- Every adjacent pair is out of order
- Maximum number of swaps are required
```

### Example 4 (Duplicate Values)

```
Input:
prices = [200, 100, 200, 50]

Output: [50, 100, 200, 200]

Explanation:

- Duplicate prices remain adjacent after sorting
- Bubble Sort preserves relative order (stable sort)
```

### Example 5 (Edge Case – Single Element)

```
Input: 
prices = [500]

Output: [500]

Explanation:

- A single element is already sorted
```

### Example 6 (Edge Case – Empty Array)

```
Input:
prices = []

Output: []

Explanation:

- No elements to sort
```

---

## ⚠️ Edge Cases to Consider

* Empty array
* Array with one element
* Already sorted array
* Reverse sorted array
* Array containing duplicate values

---

## 📏 Constraints

* `0 ≤ n ≤ 10³`
* `0 ≤ prices[i] ≤ 10⁶`

---

## 📝 Notes

* Bubble Sort works by repeatedly swapping **adjacent elements**
* After each pass, the **largest unsorted element moves to the end**

* Bubble Sort is:

  * **Stable** : order of the elements will be preserved even after sorting.
  * **In-place** : doesn't require extra space.

* Time Complexity:

  * Best Case: **O(n)** (already sorted with optimization)
  * Average Case: **O(n²)**
  * Worst Case: **O(n²)**

