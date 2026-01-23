
# InsertionSort Algorithm

## Problem Title

### Arrange Student Scores in Ascending Order

---

## Problem Description

You are given an array representing the scores of students in a classroom.
The scores are recorded in **no particular order**, and your task is to **sort the scores in ascending order**.

The sorting must rearrange the elements such that:

* The **lowest score appears first**
* The **highest score appears last**
* Duplicate scores should remain grouped together

This problem is well-suited to be solved using **Insertion Sort**, where:

* Elements are placed into their correct position step by step
* The sorted portion of the array grows gradually

### ⚠️ Edge Cases to Consider

* Empty array
* Array with one element
* Already sorted array
* Reverse sorted array
* Array containing duplicate values

---

## Input Format

* An integer array `scores`
* Each element represents a student’s score

---

## Output Format

* Return the array sorted in **ascending order**

---

## Examples

### Example 1 (Empty Array)

```
Input:
scores = []

Output:
[]

Explanation:
There are no student scores to sort, so the result is an empty array.
```

---

### Example 2 (Single Element + Already Sorted)

```
Input:
scores = [75]

Output:
[75]

Explanation:
A single score is already sorted by default.
```

---

### Example 3 (Reverse Sorted + Duplicate Values)

```
Input:
scores = [95, 90, 90, 85, 70]

Output:
[70, 85, 90, 90, 95]

Explanation:
The array is initially in descending order and contains duplicates.
After sorting, scores are arranged in ascending order with duplicates preserved.
```

---

## 📏 Constraints

* `0 ≤ n ≤ 10³`
* `0 ≤ scores[i] ≤ 100`

---

## 📝 Notes ( if any )

* The sorting should be done by **comparison-based techniques**

* Insertion Sort works by inserting elements into their correct position in a growing sorted subarray
* Insertion Sort algorithm is:

  * **In-place**
  * **Easy to implement**

* Time Complexity:

  * Insertion Sort:

    * Best Case: **O(n)** (already sorted)
    * Worst Case: **O(n²)** (reverse sorted)

* Space Complexity: **O(1)** (all cases)
---
