## Optimal Approach

### Intuition

- Think of matrix divided into 3 parts:
```
Upper Triangle → above diagonal
Diagonal       → i === j
Lower Triangle → below diagonal
```

**Rules :**
```
# Upper Triangle :
    column index ≥ row index
    → j ≥ i

# Lower Triangle :
    row index ≥ column index
    → i ≥ j
```

### Pseudo Code
```
FUNCTION matrixTrianglesSum(matrix)

    upperSum ← 0
    lowerSum ← 0

    FOR i from 0 to number_of_rows - 1
        FOR j from 0 to number_of_columns - 1

            IF i ≤ j
                upperSum ← upperSum + matrix[i][j]
            END IF

            IF i ≥ j
                lowerSum ← lowerSum + matrix[i][j]
            END IF

        END FOR
    END FOR

    RETURN (upperSum, lowerSum)

END FUNCTION
```

### Code

```js
function MatrixTrianglesSum(matrix){

    let UpperTriangleSum = 0;
    let LowerTriangleSum = 0;

    for(let i=0; i<matrix.length; i++){
        for(let j=0; j<matrix[i].length; j++){
            if(i <= j){
                UpperTriangleSum += matrix[i][j];
            }

            if(i >= j){
                LowerTriangleSum += matrix[i][j];
            }
        }
    }

    return {
        "UpperTriangleSum" : UpperTriangleSum,
        "LowerTriangleSum" : LowerTriangleSum
    }
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
