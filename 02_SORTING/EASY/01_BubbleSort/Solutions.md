
## Undertanding the Problem Statement :

```
Given, 

    integer array => arr

    TASK : Sort the array using bubble sort

    EDGE CASES :
    - if(n <= 1) : return arr;

```

## Iterative Approach :

### Pseudo Code :

```
bubbleSortIterative(arr)

    n ← length of arr

    IF n ≤ 1
        RETURN arr

    FOR i from 0 to n - 1

        swapped ← false

        FOR j from 0 to n - i - 2

            IF arr[j] > arr[j + 1]
                swap arr[j] and arr[j + 1]
                swapped ← true
            END IF

        END FOR

        IF swapped == false
            BREAK   // array is already sorted
        END IF

    END FOR

    RETURN arr

END 

```

### Code :
```js
    function BubbleSort(arr){

        let n = arr.length;

        // EDGE CASES
        if(n <= 1) return arr;


        for(let i=0; i<n; i++){
            let swap = 0;

            for(let j=0; j<n-i-1; j++){
                if(arr[j] > arr[j+1]){
                    let temp = arr[j];
                    arr[j] = arr[j+1];
                    arr[j+1] = temp;
                    swap++;
                }
            }
            
            if(swap === 0) return arr;
        }

        return arr;
    }
```

### Algorithmic Analysis :

**Time Complexity** : 
```
Best case : O(n) // when the array is sorted + use of flag variable 
worst case : O(n^2)
Average Case : O(n^2)
```

**Space Complexity** : O(1) 

---

## Recursive Approach :

### Pseudo Code :

```
BubbleSortRecursive(arr, n):

    if n <= 1
        return

    swapped ← false

    perform one bubble pass
        if any swap happens
            swapped ← true

    if swapped == false
        return   // already sorted

    BubbleSortRecursive(arr, n - 1)

END

```

### Code :
```js
function BubbleSortRecursive(arr, n){

    // base condition
    if( n <= 1) return arr;

    let swap = false;

    // Computation
    for(let i=0; i<n-1; i++){
        // swapping
        if(arr[i] > arr[i+1]){
            let temp = arr[i];
            arr[i] = arr[i+1];
            arr[i+1] = temp;
            swap = true;
        }
    }

    if(swap === false) return arr; // already the arr is sorted

    // recursive call
    return BubbleSortRecursive(arr, n-1);
}
```

### Algorithmic Analysis :

**Time Complexity** : 
```
Best case : O(n) // when the array is sorted
worst case : O(n^2)
Average Case : O(n^2)
```

**Space Complexity** :
```
O(n)   // recursion stack

- Even optimized, recursion still costs stack space.
```