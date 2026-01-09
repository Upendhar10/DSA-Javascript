
## Undertanding the Problem Statement :

```
Given, 
    integer array => arr
    positive integer => k

    Left rotate the array by k positions
    Rotations are cyclic in nature

    If `K` > arr.length, the no.of rotations should be adjusted as per the array length.
    => K = K % arr.length;

    The relative order of the remaining elements should be preserved.

    Edge cases :
    [], [i], k == 0 , k % arr.length === 0, then array remains unchanged. 
    => return arr; 

```

## Bruteforce Approach :

### Pseudo Code :

1. Let n be the length of the array

2. If n is equal to `0` OR `n` is equal to `1`:
      return the array

3. Reduce `k` using modulo:
      `k = k mod n`

4. If `k` is equal to `0`:
      return the array

5. Create an empty list called result

6. For index `i` from `k` to `(n - 1)`:
      Append array[i] to result

7. For index `i` from `0` to `(k - 1)`:
      Append array[i] to result

8. Return result


### Code :
```js
function LeftRotateArrayByKbrute(arr, k){

    let n = arr.length;
    k = k % n;

    if(k === 0 || n <= 1){
        return arr;
    }

    let result = []

    for(let i=k; i<n; i++){
        result.push(arr[i]);
    }

    for(let i=0; i<k; i++){
        result.push(arr[i]);
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

The array is divided into two logical parts

Each part is reversed independently

The entire array is then reversed

Rotation is achieved in-place.

### Pseudo Code :

1. Let `n` be the length of the array

2. Reduce `k` using modulo:
    `k = k mod n`

3. If `k` is equal to `0` OR `n` is equal to `0` OR `n` is equal to `1`:
    return the array

4. Reverse the subarray from index `0` to `(n - k - 1)`

5. Reverse the subarray from index `(n - k)` to `(n - 1)`

6. Reverse the entire array from index `0` to `(n - 1)`

7. Return the array


### Code :
```js

function reverse(start, end, arr){
    
    while(start <= end){
        let temp = arr[start];
        arr[start] = arr[end];
        arr[end] = temp;
        start++;
        end--;
    }
    return arr;
}

function RightRotateArrayByKOptimal(arr, k){
    let n = arr.length;
    k = k % n;

    if(k === 0 || n === 0 || n === 1){
        return arr;
    }
    
    reverse(0, n-k-1, arr);
    reverse(n-k, n-1, arr);
    reverse(0,n-1, arr);

    return arr;
}
```

### Algorithmic Analysis :

**Time Complexity** : O(n)

**Space Complexity** : O(1)