
## Undertanding the Problem Statement :

```
Given, 

    integer array => arr

    TASK : Sort the array using Selection sort in the descending order

    EDGE CASES :
    - if(n <= 1) : return arr;

```

## Iterative Approach :

### Pseudo Code :

```
SelectionSortIterative(arr)

    n ← length of arr

    IF n ≤ 1
        RETURN arr

    FOR i from 0 to n - 1

        maxElementIndex <- i

        FOR j from i+1 to n-1

            IF arr[j] > arr[maxElementIndex]
                maxElementIndex <- j
            END IF

        END FOR

        swap(arr[maxElementIndex], arr[start])

    END FOR

    RETURN arr

END 

```

### Code :
```js
function SelectionSortIterative(arr){

    let n = arr.length;

    // EDGE CASES
    if(n <= 1) return arr;

    for(let i=0; i<n; i++){

        let maxElemIndex = i;

        // Find the maxElemIndex
        for(let j=i; j<n; j++){
            if (arr[j] > arr[maxElemIndex]) {
                maxElemIndex = j;
            }
        }

        // swapping
        let temp = arr[maxElemIndex];
        arr[maxElemIndex] = arr[i];
        arr[i] = temp;
    }
    
    return arr;
}
```

### Algorithmic Analysis :

**Time Complexity** : 
```
Best case : O(n^2) 
worst case : O(n^2)
Average Case : O(n^2)
```

**Space Complexity** : O(1) 

---

## Recursive Approach :

### Pseudo Code :

```
SelectionSortRecursive(arr, start, end):

    if start >= end
        return arr;

    maxElementIndex <- start

    FOR j from start+1 to end

            IF arr[j] > arr[maxElementIndex]
                maxElementIndex = j
            END IF

    END FOR

    swap(arr[maxElementIndex], arr[start])
    SelectionSortRecursive(arr, start + 1, end)

END

```

### Code :
```js
function SelectionSortRecursive(arr, start, end){

    // base condition
    if(start >= end) return arr;

    // computation
    let maxElemIndex = start;
    for(let j=start+1; j <= end; j++){
        if (arr[j] > arr[maxElemIndex]) {
            maxElemIndex = j;
        }
    }
    let temp = arr[maxElemIndex];
    arr[maxElemIndex] = arr[start];
    arr[start] = temp;

    // recursive call
    return SelectionSortRecursive(arr, start + 1, end)
}
```

### Algorithmic Analysis :

**Time Complexity** : 
```
Best case : O(n^2)
worst case : O(n^2)
Average Case : O(n^2)
```

**Space Complexity** :
```
O(n)   // recursion stack

- Even optimized, recursion still costs stack space.
```