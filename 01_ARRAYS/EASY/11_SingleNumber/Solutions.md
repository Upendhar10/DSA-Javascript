
## Undertanding the Problem Statement :

```
Given, 

    integer array => arr

    In `arr`:
     - One number is unique 
     - All other numbers are repeated twice
    
    TASK : Find that Unique Number.

    EDGE CASE :
    - If array has only one element => return that element

```

## Bruteforce Approach :

### Pseudo Code :

```
FUNCTION findSingleNumberBruteforce(arr)

    n ← length of arr

    IF n == 1
        RETURN arr[0]

    FOR i from 0 to n - 1

        count ← 0

        FOR j from 0 to n - 1
            IF arr[i] == arr[j]
                count ← count + 1
        END FOR

        IF count == 1
            RETURN arr[i]
        END IF

    END FOR

    RETURN -1

END FUNCTION


```

### Code :
```js
function SingleNumberBF(arr){

    let n = arr.length;

    // EDGE CASE
    if(n === 1) return arr[0];

    for (let i = 0; i < n; i++) {
        let count = 0;
        for (let j = 0; j < n; j++) {
            if (nums[i] == nums[j])
                count++;
        }
        if (count == 1) return nums[i];
    }

    return -1;
}
```

### Algorithmic Analysis :

**Time Complexity** : O(n^2)

**Space Complexity** : O(1) 

---

## Optimal Approach :

### Intuition :

- Think of `XOR` as a comparison-based cancellation tool.

- The key property we exploit:
    > Same number appearing twice cancels itself out

- So if:
    - The array contains all repeated numbers except one
    - Then XOR-ing everything together will leave only the missing number.

**- Three Properties of `XOR`**:
1. `x XOR x = 0` ; XOR-ing two same numbers results in `0`
2. `x XOR 0 = x` ; XoR-ing any number with `0` results in that number
3. `a XOR b XOR c = c XOR a XOR b` ; order doesn't matter in `XOR` operation

### Pseudo Code :

```
FUNCTION findSingleNumberOptimal(arr)

    n ← length of arr

    IF n == 1
        RETURN arr[0]

    xorResult ← 0

    FOR i from 0 to n - 1
        xorResult ← xorResult XOR arr[i]
    END FOR

    RETURN xorResult

END FUNCTION

```

### Code :
```js
function SingleNumberOptimal(arr){

    let n = arr.length;

    // EDGE CASE
    if(n === 1) return arr[0];

    let XOR = 0;

    for(let i=0; i<n; i++){
        XOR = XOR ^ arr[i];
    }

    return XOR;
}
```

### Algorithmic Analysis :

**Time Complexity** : O(n)

**Space Complexity** : O(1) 