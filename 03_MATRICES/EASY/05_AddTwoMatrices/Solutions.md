## Bruteforce Approach

### Intuition
- Matrix addition is element-wise
- Only valid when both matrices have same dimensions
- Each element at position (i, j) in the result is:
```
result[i][j] = mat1[i][j] + mat2[i][j]
```

- How to think:
    - Fix a row
    - Traverse all columns in that row
    - Add corresponding elements
    - Store the result

### Pseudo Code
```
FUNCTION addTwoMatrices(mat1, mat2)

    IF mat1 is empty OR mat2 is empty
        RETURN "Invalid Matrices"

    IF number of rows in mat1 ≠ number of rows in mat2
        RETURN "Invalid Matrices"

    result ← empty matrix

    FOR i from 0 to number_of_rows - 1

        IF number of columns in mat1[i] ≠ number of columns in mat2[i]
            RETURN "Invalid Matrices"

        row ← empty list

        FOR j from 0 to number_of_columns - 1
            sum ← mat1[i][j] + mat2[i][j]
            ADD sum to row
        END FOR

        ADD row to result
    END FOR

    RETURN result

END FUNCTION

```

### Code
```js
function AddTwoMatricesBF(mat1, mat2){

    // EDGE CASE
    // number of rows in both matrices should be equal
    if(mat1.length !== mat2.length) return "Invalid Matrices";

    let result = [];

    for(let i=0; i<mat1.length; i++){

        // number of columns in both matrices should be equal
        if(mat1[i].length !== mat2[i].length) return "Invalid Matrices"

        let row = [];
        for(let j=0; j<mat1[i].length; j++){
            let sum = mat1[i][j] + mat2[i][j];
            row.push(sum);
        }
        result.push(row);
    }

    return result;
}
```

### Algorithmic Analysis

**Time Complexity** : O(n x m)
```
where, 
n => no.of rows
m => no.of columns
```

**Space Complexity** : O(n x m)
```
- for storing the resultant matrix
```

----

## Optimal Approach

### Intuition

- Instead of creating a new matrix:
    - Modify mat1 directly
    - Saves space

- But mutates input, which should be clearly communicated

### Pseudo Code
```
FUNCTION AddTwoMatricesOptimal(mat1, mat2)

    IF mat1 is empty OR mat2 is empty
        RETURN "Invalid Matrices"

    IF number of rows in mat1 ≠ number of rows in mat2
        RETURN "Invalid Matrices"

    FOR i from 0 to number_of_rows - 1

        IF number of columns in mat1[i] ≠ number of columns in mat2[i]
            RETURN "Invalid Matrices"

        FOR j from 0 to number_of_columns - 1
            mat1[i][j] ← mat1[i][j] + mat2[i][j]
        END FOR

    END FOR

    RETURN mat1

END FUNCTION

```

### Code
```js
function AddTwoMatricesOptimal(mat1, mat2){

    // EDGE CASE
    // number of rows in both matrices should be equal
    if(mat1.length !== mat2.length) return "Invalid Matrices";


    for(let i=0; i<mat1.length; i++){

        // number of columns in both matrices should be equal
        if(mat1[i].length !== mat2[i].length) return "Invalid Matrices"

        for(let j=0; j<mat1[i].length; j++){
            let sum = mat1[i][j] + mat2[i][j];
            mat1[i][j] = sum;
        }
    }

    return mat1;
}
```

### Algorithmic Analysis

**Time Complexity** : O(n x m)
```
where,
n => no.of rows
m = no.of columns
```

**Space Complexity** : O(1)
```
- Storing back the result in mat1 by modifying the original matrix.
- Although there is no extra space required, but altering the Inputs (unless specified) is not a good practise.
```