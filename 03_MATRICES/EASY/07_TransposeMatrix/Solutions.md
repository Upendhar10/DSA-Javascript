## Optimal Approach

### Intuition

- The transpose of a matrix means:
    - Convert rows → columns
    - Convert columns → rows

Example :
```
Original (2×3):
1 2 3
4 5 6

Transpose (3×2):
1 4
2 5
3 6
```

**1. Square Matrix (rows = columns)**
- We can transpose in-place (no extra space)
- Just swap elements across the diagonal: (i, j) ↔ (j, i)
- Only swap when i < j to avoid double swapping

**2. Rectangular Matrix (rows ≠ columns)**
- We cannot transpose in-place (shape changes)
- So you create a new matrix
- Fill it such that: result[i][j] = matrix[j][i]

### Pseudo Code

```
FUNCTION MatrixTranspose(matrix, rows, columns)

    IF rows == columns THEN
        RETURN SquareMatrixTranspose(matrix, rows, columns)
    ENDIF

    CREATE empty result matrix

    FOR i FROM 0 TO columns - 1
        CREATE empty row

        FOR j FROM 0 TO rows - 1
            ADD matrix[j][i] TO row
        END FOR

        ADD row TO result
    END FOR

    RETURN result

END FUNCTION

FUNCTION SquareMatrixTranspose(matrix, rows, columns)

    FOR i FROM 0 TO rows - 1
        FOR j FROM 0 TO columns - 1

            IF i < j THEN
                temp = matrix[i][j]
                matrix[i][j] = matrix[j][i]
                matrix[j][i] = temp
            ENDIF

        END FOR
    END FOR

    RETURN matrix

END FUNCTION
```

### Code

```js
function MatrixTranspose(matrix, rows, columns){

    if(rows === columns) {
        return SquareMatrixTranspose(matrix, rows, columns);
    }

    let result = [];

    for(let i=0; i<columns; i++){
        let row = [];
        for(let j=0; j<rows; j++) {
            row.push(matrix[i][j])
        }
        result.push(row);
    }
    
    return result;
}

function SquareMatrixTranspose(matrix, rows, columns){

    for(let i=0; i<rows; i++){
        for(let j=0; j<columns; j++){
            if(i < j) {
                let temp = matrix[i][j] 
                matrix[i][j] = matrix[j][i]
                matrix[j][i] = temp
            }
        }
    }
    return matrix;
}
```

### Algorithmic Analysis

**Time Complexity** : 
- Square Matrix (rows = columns) : O(rows x columns) 
- Rectangular Matrix (rows ≠ columns) : O(rows x columns)

**Space Complexity** :
- Square Matrix (rows = columns) : O(1) 
- Rectangular Matrix (rows ≠ columns) : O(rows x columns)