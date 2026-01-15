
## Undertanding the Problem Statement :

```
Given, 

    integer array => arr
    range => 1 to n
    arr.length => n-1

    `arr` contains :
     - Unique integers
     - range from 1 to n (inclusive)
     - One number is missing in this range
    
    TASK : Find that missing Number.

    EDGE CASE :
    - Empty array AND n == 1 => return 1

```

## Bruteforce Approach :

### Intuition:

- Check every number from 1 to n and see whether it exists in the array.
- The first number that is not present is the missing number.

### Pseudo Code :
```
FUNCTION findMissingNumberBruteforce(arr, n)

    IF n == 1 AND arr is empty
        RETURN 1

    FOR i from 1 to n
        IF i is NOT present in arr
            RETURN i
    END FOR

END FUNCTION

```

**NOTE** :

- `includes()` makes this expensive ; as it takes O(n) time

### Code :
```js
function MissingNumberRangeBF(arr, n){

    let missingNum = 0;

    // Edge case
    if(n === 1 && arr.length === 0){
        missingNum = 1;
        return missingNum;
    }

    // i => range from 1 to n (inclusive)
    for(let i=1; i<=n; i++){
        if(!arr.includes(i)){
            missingNum = i;
            break;
        }
    }

    return missingNum;
}
```

### Algorithmic Analysis :

**Time Complexity** : O(n^2)
```
`includes()` takes O(n) time for each iteration
```
**Space Complexity** : O(1)

---

## Better Approach :

### Intuition :

- The sum of numbers from 1 to n is known
- Subtract the sum of array elements from the expected sum
- The difference is the missing number

**NOTE**: 
- The sum formula can overflow for large `n`, although it wasn't reflected in the time complexity

### Pseudo Code :

```
FUNCTION findMissingNumberBetter(arr, n)

    rangeSum ← (n × (n + 1)) / 2
    actualSum ← 0

    FOR each element in arr
        actualSum ← actualSum + element
    END FOR

    missingNumber ← rangeSum − actualSum

    RETURN missingNumber

END FUNCTION

```

### Code :
```js
function MissingNumberRangeBetter(arr, n){

    let missingNum = -1;

    let rangeSum = Math.floor((n * (n+1))/2);

    let arraySum = 0;

    arr.forEach(element => {
        arraySum += element;
    });

    missingNum = rangeSum - arraySum;

    return missingNum;
}
```

### Algorithmic Analysis :

**Time Complexity** : O(n)

**Space Complexity** : O(1) 

---

## Optimal Approach :

### Intuition :

- Think of `XOR` as a comparison-based cancellation tool.

- The key property we exploit:
    > Same number appearing twice cancels itself out

- So if:
    - One list contains numbers 1 → n
    - Another list contains all numbers except one
    - Then XOR-ing everything together will leave only the missing number.

**- Three Properties of `XOR`**:
1. `x XOR x = 0` ; XOR-ing two same numbers results in `0`
2. `x XOR 0 = x` ; XoR-ing any number with `0` results in that number
3. `a XOR b XOR c = c XOR a XOR b` ; order doesn't matter in `XOR` operation

### Pseudo Code :

```
FUNCTION findMissingNumberUsingXOR(arr, n)

    xorResult ← 0

    // XOR all numbers from 1 to n
    FOR i from 1 to n
        xorResult ← xorResult XOR i
    END FOR

    // XOR all elements of the array
    FOR each element in arr
        xorResult ← xorResult XOR element
    END FOR

    RETURN xorResult

END FUNCTION
```

### Code :
```js
function MissingNumberRangeOptimal(arr, n){

    let MissingNumber = -1;

    let xorRange = 0, xorArray = 0;

    for(let i=1; i<=n; i++){
        xorRange = xorRange ^ i;
    }

    for(let i=0; i<arr.length; i++){
        xorArray = xorArray ^ arr[i];
    }

    MissingNumber = xorRange ^ xorArray;

    return MissingNumber;
}
```

### Algorithmic Analysis :

**Time Complexity** : O(n)

**Space Complexity** : O(1) 