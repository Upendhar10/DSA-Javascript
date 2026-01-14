
## Undertanding the Problem Statement :

```
Given, 

    - Two Interger arrays => arr1 & arr2
    - Two arrays are sorted in ascending order (with duplicates)

    Union of two arrays :
    - Collection of distinct elements in arr1 & arr2
    - Result array should contain unique values
    - strictly sorted in ascending order

    EdgeCases :
    - both arrays are empty => union array will be empty
    - if one of the array is empty => union array should consists of elements of non-empty array (without duplicates)

```

## Bruteforce Approach :

### Intuition:

- we can think in terms of set behavior:

- A Set automatically:
    - Removes duplicates
    - Maintains insertion order (important in JS)

- Inserting elements from both arrays into a single set guarantees:
    - Uniqueness
    - Coverage of all elements

- Since a Set stores only unique values, inserting all elements from both arrays into a Set automatically gives the union

### Pseudo Code :
```
FUNCTION unionUsingSet(arr1, arr2)

    uniqueSet ← empty set

    FOR each element in arr1
        insert element into uniqueSet

    FOR each element in arr2
        insert element into uniqueSet

    result ← convert uniqueSet to array

    RETURN result

END FUNCTION

```

**NOTE** :

- Output is NOT guaranteed to be sorted
    - If arrays are sorted and order matters:
    - This solution breaks sorted order
    - Extra sorting step needed → O((n+m) log(n+m))

### Code :
```js
function findUnionArrayBF(arr1, arr2){

    let n = arr1.length;
    let m = arr2.length;

    // Edge cases
    if(n === 0 && m === 0) return [];

    let uniqueSet = new Set();

    for(let i=0; i<n; i++){
        uniqueSet.add(arr1[i]);
    }

    for(let i=0; i<m; i++){
        uniqueSet.add(arr2[i]);
    }

    return Array.from(uniqueSet);
}
```

### Algorithmic Analysis :

**Time Complexity** : O(n+m)
```
Set insertion is average O(1) in JavaScript
```

**Space Complexity** : O(n+m) + O(n+m)
```
Set → O(n + m)
Result array → O(n + m)
```
---

## Optimal Approach :

### Intuition :

- Since both arrays are already sorted, we can use the two-pointer technique.

- At any moment:
    - One pointer points to the current element of the first array
    - The other pointer points to the current element of the second array

- There are only three possible comparisons:
    - First element is smaller
    - Second element is smaller
    - Both elements are equal

- Duplicate handling becomes easy:
    - Because the arrays are sorted, duplicates will appear adjacent
    - We only insert a value if it is different from the last inserted value in the union array

- Once one array is exhausted:
    - Append remaining elements from the other array
    - Still ensure no duplicates

### Pseudo Code :

```
FUNCTION findUnion(arr1, arr2)

    i ← 0
    j ← 0
    union ← empty list

    WHILE i < length(arr1) AND j < length(arr2)

        IF arr1[i] < arr2[j]
            IF union is empty OR last element of union ≠ arr1[i]
                add arr1[i] to union
            i ← i + 1

        ELSE IF arr1[i] > arr2[j]
            IF union is empty OR last element of union ≠ arr2[j]
                add arr2[j] to union
            j ← j + 1

        ELSE    // arr1[i] == arr2[j]
            IF union is empty OR last element of union ≠ arr1[i]
                add arr1[i] to union
            i ← i + 1
            j ← j + 1

    END WHILE


    WHILE i < length(arr1)
        IF union is empty OR last element of union ≠ arr1[i]
            add arr1[i] to union
        i ← i + 1
    END WHILE


    WHILE j < length(arr2)
        IF union is empty OR last element of union ≠ arr2[j]
            add arr2[j] to union
        j ← j + 1
    END WHILE


    RETURN union

END FUNCTION
```

### Code :
```js
function findUnionArrayOptimal(arr1, arr2){

    let n = arr1.length;
    let m = arr2.length;

    // Edge cases
    if(n === 0 && m === 0) return [];

    let unionArr = [];

    let pointerI = 0, pointerJ = 0;

    // Union array should have a unique values
    while(pointerI < n && pointerJ < m){
        if(arr1[pointerI] < arr2[pointerJ]){
            if(unionArr[unionArr.length-1] !== arr1[pointerI]){
                unionArr.push(arr1[pointerI]);
            }
            pointerI++;
        }else if(arr1[pointerI] > arr2[pointerJ]) {
            if(unionArr[unionArr.length-1] !== arr2[pointerJ]){
                unionArr.push(arr2[pointerJ]);
            }
            pointerJ++;
        }else if(arr1[pointerI] == arr2[pointerJ]) {
            if(unionArr[unionArr.length-1] !== arr1[pointerI]){
                unionArr.push(arr1[pointerI]);
            }
            pointerI++;                
            pointerJ++;
        }
    }

    // when any one of the array got exhausted
    while( pointerI < n ){
        if(unionArr[unionArr.length-1] !== arr1[pointerI]){
            unionArr.push(arr1[pointerI])
        }
        pointerI++;
    }
    
    while(pointerJ < m){
        if(unionArr[unionArr.length-1] !== arr1[pointerJ]){
            unionArr.push(arr2[pointerJ])
        }
        pointerJ++;
    }

    return unionArr;
}
```

### Algorithmic Analysis :

**Time Complexity** : O(n+m)

**Space Complexity** : O(n+m)