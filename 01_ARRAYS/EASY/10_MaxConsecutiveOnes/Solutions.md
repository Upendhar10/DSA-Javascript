## Optimal Approach :

### Intuition:
- Keep counting consecutive `1`s and reset the count whenever a `0` appears, while tracking the maximum count.

---

### Pseudo Code:
```
FUNCTION findMaxConsecutiveOnes(arr)

    n ← length of arr

    IF n == 0
        RETURN 0

    maxConsOnes ← 0
    currentCount ← 0

    FOR i from 0 to n - 1

        IF arr[i] == 1
            currentCount ← currentCount + 1
        ELSE
            currentCount ← 0
        END IF

        maxConsOnes ← maximum(maxConsOnes, currentCount)

    END FOR

    RETURN maxConsOnes

END FUNCTION
```
---

### Code:
```js
function MaxConsecutiveOnesOptimal(arr){

    let n = arr.length;

    // Egde cases
    if(n === 0) return 0;

    let maxConsOnes = 0;
    let count = 0;

    for(let i=0; i<n; i++){
        
        // a[i] === 0; count = 0;
        // a[i] === 1; count++;

        if(arr[i] === 1) {
            count++;
        }else {
            count = 0;
        }

        maxConsOnes = Math.max(count, maxConsOnes)
    }

    return maxConsOnes;
}
```
---

### Algorithm Analysis:

**Time Complexity** : O(n)

**Space Complexity** : O(1)
