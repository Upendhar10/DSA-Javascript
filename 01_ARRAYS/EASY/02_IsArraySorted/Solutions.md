## Understanding the Problem Statement:
```
Given,
  integer array => arr

  // Edge case
  empty array => true // sorted array
  single element array => true // sorted array

  // Idea :
    non-decreasing order => ascending order with duplicate elements.

    At any index, currElement should be less than or equal to the element in the immediate next index. 
  
```

## Optimal Approach

### Pseudo Code :

1. Check for Edgecase
    - if ( arr.length >= 1) return false
2. Traverse the given the array 
    - At any point the currElement is greater than the element in the immediate next Index, return false.

### Code :
```js
function isArrayIsSorted(arr){

    let n = arr.length;

    // Edge cases
    if( n <= 1) {
        return true;
    }

    for(let i=0; i<n; i++){
        if(arr[i] > arr[i+1]){
            return false;
        }
    }
    return true;
}
```
### Algorithmic Analysis:

**Time Complexity:** O(n)

**Space Complexity:** O(1)