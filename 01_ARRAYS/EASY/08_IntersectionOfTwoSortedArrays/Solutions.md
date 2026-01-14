
## Undertanding the Problem Statement :

```
Given, 

    - Two Interger arrays => arr1 & arr2
    - Two arrays are sorted in ascending order (with duplicates)

    Intersection of two arrays :
    - Elements that are present in both arrays
    - Result array should contain unique values
    - strictly sorted in ascending order

    EdgeCases :
    - if both arrays are empty => Insertion array will be empty
    - if one of the array is empty => Insertion array will be empty
    - If there are no common elements in both arrays => Insertion array will be empty
```

## Bruteforce Approach :

### Intuition:

- we can think in terms of set behavior:

- A Set automatically:
    - Removes duplicates
    - Maintains insertion order (important in JS)

- Since a Set stores only unique values, inserting all elements from dummy array into a Set automatically gives the intersection.

### Pseudo Code :
```
FUNCTION intersectionBruteforce(arr1, arr2)

    resultList ← empty list

    FOR each element in arr1
        IF element exists in arr2
            add element to resultList

    uniqueSet ← empty set

    FOR each element in resultList
        insert element into uniqueSet

    RETURN elements of uniqueSet as array

END FUNCTION
```

**NOTE** :

- `includes()` makes this expensive ; as it takes O(m) time
- Bruteforce solution ignores that advantage of arrays being sorted already
- Extra data structures such as dummy array, Set and Output array

### Code :
```js
function InsertionArrayBF(arr1, arr2){

    let n = arr1.length;
    let m = arr2.length;

    // Edge case
    if((n <= 0 || m <= 0) || ( n+m <= 0)) return [];

    let dummy = [];

    for(let i=0; i<n; i++){
        if(arr2.includes(arr1[i])) dummy.push(arr1[i]);
    }

    let uniqueSet = new Set();

    for(let i=0; i<dummy.length; i++){
        uniqueSet.add(dummy[i]);
    }

    return Array.from(uniqueSet);
}
```

### Algorithmic Analysis :

**Time Complexity** : O(n x m)
```
Set insertion is average O(1) in JavaScript
`includes()` takes O(m) time for each iteration
```

**Space Complexity** : O(n)
```
dummy + set + result
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
    - We only insert a value if it is different from the last inserted value in the intersection array

### Pseudo Code :

```
FUNCTION intersectionOptimal(arr1, arr2)

    i ← 0
    j ← 0
    intersection ← empty list

    WHILE i < length(arr1) AND j < length(arr2)

        IF arr1[i] == arr2[j]
            IF intersection is empty OR last element ≠ arr1[i]
                add arr1[i] to intersection
            i ← i + 1
            j ← j + 1

        ELSE IF arr1[i] < arr2[j]
            i ← i + 1

        ELSE
            j ← j + 1

    END WHILE

    RETURN intersection

END FUNCTION

```

### Code :
```js
function InsertionArrayOptimal(arr1, arr2){

    let n = arr1.length;
    let m = arr2.length;

    // Edge case
    if((n <= 0 || m <= 0) || ( n+m <= 0)) return [];

    let intersectionArr = [];

    let pointerI = 0, pointerJ = 0;

    while(pointerI < n && pointerJ < m){

        if(arr1[pointerI] === arr2[pointerJ]){
            if(intersectionArr[intersectionArr.length -1] !== arr1[pointerI]){
                intersectionArr.push(arr1[pointerI]);
            }
            pointerI++;
            pointerJ++;
        }else if(arr1[pointerI] < arr2[pointerJ]) {
            pointerI++;
        }else if(arr1[pointerI] > arr2[pointerJ]){
            pointerJ++;
        }
    } 

    return intersectionArr;
}
```

### Algorithmic Analysis :

**Time Complexity** : O(n+m)

**Space Complexity** : O(1) 
```
O(1) => extra space
O(k) => output array, k = size of intersertion array
```