
## Undertanding the Problem Statement :

```
Given, 

    integer arr => arr

    task : move all occurences of `0` to the end of the array

    conditions:
        1. Relative order of the non-zero elements should be maintained (including duplicate non-zero elements)
        2. Should perform Inplace Operation.

    Edge cases :
        - [],[i],[non-zero],[onlyZeros] => remains unchanged
        - array might contains negative numbers
        - Zeroes can be appeared at beginning,middle or end

```

## Bruteforce Approach :

### Pseudo Code :

1. Let n be the length of the array

2. If n is less than or equal to 1:
      return the array

3. If the array does not contain any zero:
      return the array

4. Initialize a variable zerosCount to 0

5. Traverse the array:
      If the current element is equal to 0:
            Increment zerosCount

6. Create an empty list called result

7. Traverse the array again:
      If the current element is not equal to 0:
            Append the element to result

8. While zerosCount is greater than 0:
      Append 0 to result
      Decrement zerosCount by 1

9. Return result

### Code :
```js
function MoveZerosToEndBF(arr){

    let n = arr.length;

    if(n <= 1) return arr;

    if(!arr.includes(0)) return arr;

    let zerosCount = 0;

    arr.forEach(element => {
        if(element === 0) zerosCount++;
    });

    let result = [];

    for (let index = 0; index < n; index++) {
        if(arr[index] !== 0){
            result.push(arr[index]);
        }
    }

    while(zerosCount > 0){
        result.push(0);
        zerosCount--;
    }

    return result;
}
 
```

### Algorithmic Analysis :

**Time Complexity** : O(n)

**Space Complexity** : O(n)
```
- Auxilliary Space for storing the result arr.
```

---

## Optimal Approach :

### Intuition :
Maintain a pointer (iPointer) pointing to the first zero

Traverse remaining elements

Whenever a non-zero is found → swap it with the zero position

This shifts zeros to the end in-place with O(1) extra space

### Pseudo Code :

```
FUNCTION MoveZerosToEndOptimal(arr)

    n ← length of arr

    IF n ≤ 1
        RETURN arr
    END IF

    IF arr does NOT contain 0
        RETURN arr
    END IF

    iPointer ← 0

    // Step 1: Find index of first zero
    FOR i FROM 0 TO n - 1
        IF arr[i] = 0
            iPointer ← i
            BREAK
        END IF
    END FOR

    // Step 2: Swap non-zero elements with zero position
    FOR j FROM iPointer + 1 TO n - 1
        IF arr[j] ≠ 0
            SWAP arr[j] WITH arr[iPointer]
            iPointer ← iPointer + 1
        END IF
    END FOR

    RETURN arr

END FUNCTION
```

### Code :
```js
function MoveZerosToEndOptimal(arr){
    
    let n = arr.length;

    if(n <= 1) return arr;

    if(!arr.includes(0)) return arr;

    let iPointer = 0;

    // first 0th element index
    for(let i=0; i<n; i++){
        if(arr[i] === 0){
            iPointer = i;
            break;
        }
    }

    for(let j=iPointer+1; j < n; j++){
        if(arr[j] !== 0){
            let temp = arr[j];
            arr[j] = arr[iPointer];
            arr[iPointer] = temp;   
            iPointer++;  
        }
    }
    
    return arr;
}
```

### Algorithmic Analysis :

**Time Complexity** : O(n)

**Space Complexity** : O(1)