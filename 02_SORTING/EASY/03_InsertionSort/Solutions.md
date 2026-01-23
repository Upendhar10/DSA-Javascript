
## Undertanding the Problem Statement :

```
Given, 

    integer array => arr

    TASK : Sort the array using Insertion sort in the ascending order

    INSERTION SORT WORKING:
    - Insertion works by inserting elements into their correct position in a growing subarray.

    EDGE CASES :
    - if(n <= 1) : return arr;

```

## Iterative Approach :

### Pseudo Code :

```
INSERTION_SORT_ITERATIVE(arr)

    n ← length of arr

    IF n ≤ 1
        RETURN arr

    FOR i ← 1 TO n - 1
        j ← i

        WHILE j > 0
            IF arr[j] < arr[j - 1]
                SWAP arr[j] and arr[j - 1]
            ELSE
                BREAK   // array already sorted till this point
            END IF

            j ← j - 1
        END WHILE
    END FOR

    RETURN arr
END

```

### Code :
```js
function InsertionSortIterative(arr){

    let n = arr.length;

    // EDGE CASE
    if(n <= 1) return arr;

    for(let i=1; i<n; i++){
        let j = i;

        while(j > 0){
            if(arr[j] < arr[j-1]){
                let temp = arr[j];
                arr[j] = arr[j-1];
                arr[j-1] = temp;
            }else{
                break; // optimization
            }
            j--;
        }
    }
    return arr;
}
```

### Algorithmic Analysis :

**Time Complexity** : 
```
Best case : O(n) 
worst case : O(n^2)
Average Case : O(n^2)
```

**Space Complexity** : O(1) 

---

## Recursive Approach :

### Pseudo Code :

```
INSERTION_SORT_RECURSIVE(arr, index)

    IF index ≥ length of arr
        RETURN arr

    j ← index

    WHILE j > 0
        IF arr[j] < arr[j - 1]
            SWAP arr[j] and arr[j - 1]
        ELSE
            BREAK   // no more shifting required
        END IF

        j ← j - 1
    END WHILE

    CALL INSERTION_SORT_RECURSIVE(arr, index + 1)

    RETURN arr
END

```

### Code :
```js
function InsertionSortRecursive(arr, start){

    // base condition
    if(start >= arr.length) return arr;

    // Computation
    let j = start;
    while(j > 0){
        if(arr[j] < arr[j-1]){
                let temp = arr[j];
                arr[j] = arr[j-1];
                arr[j-1] = temp;
        }else{
            break; // optimization
        }
        j--;
    }

    // recursive call
    return InsertionSortRecursive(arr, start + 1)
}
```

### Algorithmic Analysis :

**Time Complexity** : 
```
Best case : O(n)
worst case : O(n^2)
Average Case : O(n^2)
```

**Space Complexity** :
```
O(n)   // recursion stack

- Even optimized, recursion still costs stack space.
```