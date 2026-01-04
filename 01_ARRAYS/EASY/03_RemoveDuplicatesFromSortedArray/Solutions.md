## Understanding the Problem Statement:
```
Given, 

    Sorted array => non - decreasing order
    return k => no.of unique values

    conditions :
    - Inplace Operation
    - Relative order should be preserved

    Edge Cases :
    - Empty array => [] => return 0;
    - Single element array => [0] => return 1
```

---
## Bruteforce Approach:

### Pseudo Code:

1. Let n be the length of the array

2. If n is equal to 0: return 0

3. If n is equal to 1: return 1

4. Create an empty set called uniqueSet

5. For each element in the array:
    
    Add the element to uniqueSet

6. Return the size of uniqueSet


### Code:

```js
function RemoveDuplicatesBF(arr){

    let n = arr.length;

    // Edgecases
    if(arr.length === 0) return 0;

    if(arr.length === 1) return 1;

    let uniqueSet = new Set();

    for(let i=0; i<arr.length; i++){
        uniqueSet.add(arr[i]);
    }

    return uniqueSet.size;
}
```

### Algorithmic Analysis :

**Time Complexity : O(n)**
```
O(n) => Traversing the array
0(1) => Inserting single element into the set (in Javascript)
        => 1 x n => O(n)
O(n) + O(n) => O(2n) => O(n)
```

**Space Complexity : O(n)**

```
O(n) => Because we might use `n` size set in the worst case (if all elements in the given array are unqiue)
```

---

## Optimal Aprroach

### Pseudo code :

1. If the array length is 0: return 0

2. Initialize pointer i = 0
   (i represents the index of the last unique element)

3. For pointer j from index 1 to end of the array:
    
    If array[j] is not equal to array[i]: 
    
    i = i + 1, Place array[j] at index i

4. Return i + 1
   (This represents the count of unique elements)
---

### Code :
```js
function RemoveDuplicatesOptimal(arr){

    if(arr.length === 0) return 0;

    let i = 0;

    for(let j=1; j < arr.length; j++){
        if(arr[i] != arr[j]){
            arr[++i] = arr[j];
        }
    }
    console.log(arr);
    
    return i+1;
}
```

---
### Algorithmic Analysis :

**Time Complexity : O(n)**

**Space Complexity : O(1)**
