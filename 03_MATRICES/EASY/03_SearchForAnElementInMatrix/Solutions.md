## Optimal Approach

### Intuition
- A matrix is a collection of rows
- To search an element:
    - Visit every cell
    - Compare current element with the target
- As soon as the target is found:
    - Stop searching
    - Return success
- This is the most basic and safest approach, works for any type of matrix.

### Pseudo Code
```
FUNCTION linearSearchInMatrix(matrix, target)

    IF number of rows in matrix == 0
        RETURN false

    FOR row from 0 to number_of_rows - 1
        FOR col from 0 to number_of_columns_in_row - 1
            IF matrix[row][col] == target
                RETURN true
            END IF
        END FOR
    END FOR

    RETURN false

END FUNCTION

```

### Code
```js
function LinearSearchInMatrix(mat, target){

    // EDGE CASES
    if(mat.length === 0) return "Empty Matrix"
    if(mat.length === 1){
        if(mat[0][0] === target){
            return true;
        }
    }

    // Searching In Matrix
    for(let i=0; i<mat.length; i++){
        for(let j=0; j<mat[i].length; j++){
            if(mat[i][j] === target){
                console.log(`Element First Found At Indices: (${i},${j})`);
                return true;
            }
        }
    }

    return false;
}
```

### Algorithmic Analysis

**Time Complexity** : O(n x m)
```
where, 
n => no.of rows
m => no.of columns
```

**Space Complexity** : O(1)