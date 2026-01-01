## 🧩 Problem Statement

### Second Largest Element in an Array

### 📜 Description

You are given an array of integers of size **n**. Your task is to find the **second largest element** present in the array.

- If the array contains less than two distinct elements, return `-1` (since the second largest does not exist).

### 🧪 Examples
    
```
Input :
   n = 6  
   arr = [12, 35, 1, 10, 34, 1]
    
Output : 34
    
Explanation:
   The largest element is 35, and the second largest is 34.
```
    
```
Input :
   n = 5  
   arr = [10, 10, 10, 10, 10]
    
Output : -1
    
Explanation :
   Since all elements are equal, there is no second largest element.
```
    
### ⚙️ Constraints:
```
2 ≤ n ≤ 10^5
10^9 ≤ arr[i] ≤ 10^9
```