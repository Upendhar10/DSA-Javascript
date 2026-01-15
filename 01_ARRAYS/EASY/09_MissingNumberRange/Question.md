
## Problem Statement: 

### Find the Missing Number (1 to n)

You are given an array `arr` containing **`n − 1` distinct integers**, where each integer is in the **range from `1` to `n` (inclusive)**.
The array represents a sequence in which **exactly one number is missing**.

Your task is to **identify and return the missing number**.

---

## Input Constraints

* The array contains **distinct integers only**
* All elements are in the range **1 to n**
* The array size is **n − 1**
* Exactly **one number is missing**
* The array **may not be sorted**

---

## Expected Behavior & Edge Cases

Your solution must correctly handle the following scenarios:

1. **Missing number is the first element**

   * Example: `arr = [2, 3, 4, 5]`, `n = 5`
   * Output: `1`

2. **Missing number is the last element**

   * Example: `arr = [1, 2, 3, 4]`, `n = 5`
   * Output: `5`

3. **Missing number is somewhere in the middle**

   * Example: `arr = [1, 2, 4, 5]`, `n = 5`
   * Output: `3`

4. **Array is unsorted**

   * Example: `arr = [3, 1, 5, 2]`, `n = 5`
   * Output: `4`

5. **Minimum valid input**

   * Example: `arr = []`, `n = 1`
   * Output: `1`

6. **Single element missing from a two-element range**

   * Example: `arr = [1]`, `n = 2`
   * Output: `2`

---

## **Output**

* Return the **missing number** from the range `1` to `n`.

---

## **Constraints**

* `1 ≤ n ≤ 10⁶`
* Time complexity should be **O(n)**
* Extra space usage should be **O(1)** (preferred)

---

## **Notes**

* The input array **does not contain duplicates**
* Exactly **one number is guaranteed to be missing**
* You may assume the input always satisfies the above constraints


