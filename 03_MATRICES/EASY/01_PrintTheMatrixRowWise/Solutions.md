## Optimal Approach

### Intuition

- A matrix is essentially an array of rows
- In row-wise traversal:
    - Fix a row
    - Traverse all columns of that row

    So:
    - Outer loop → rows
    - Inner loop → columns

- Think of it like reading text:
- Finish one row completely, then move to the next row.

### Pseudo Code

```
FUNCTION printMatrixRowWise(matrix)

    result ← empty list

    FOR i from 0 to number_of_rows - 1
        row ← empty list

        FOR j from 0 to number_of_columns_in_row_i - 1
            ADD matrix[i][j] to row
        END FOR

        ADD row to result
    END FOR

    RETURN result
END FUNCTION

```

### Code

```js
function printMatrixRowWise(mat){
    let result = [];
    for(let i=0; i<mat.length; i++){
        let row = [];
        for(let j=0; j<mat[i].length; j++){
            row.push(mat[i][j]);
        }
        result.push(row)
    }
    return result.toString()
}
```

### Algorithmic Analysis

**Time Complexity** : O(n x m)
```
where, 
n = length of the row
m = length of the column
```

**Space Complexity** : O(n x m)
```
O(n x m) // for resultant array
O(1) // Just printing the elements
```