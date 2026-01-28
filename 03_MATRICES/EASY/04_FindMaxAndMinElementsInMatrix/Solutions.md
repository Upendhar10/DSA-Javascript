## Optimal Approach

### Intuition
- Assume:
    - First element is the smallest and largest (or use ±Infinity)

- Traverse every element:
    - Update Max if current element is larger
    - Update Min if current element is smaller

- At the end:
    - You have the global minimum and maximum

- This guarantees correctness because every element is checked once.

### Pseudo Code
```
FUNCTION findMaxAndMinInMatrix(matrix)

    IF number of rows == 0 OR number of columns == 0
        RETURN "EMPTY MATRIX"

    minValue ← +∞
    maxValue ← -∞

    FOR row from 0 to number_of_rows - 1
        FOR col from 0 to number_of_columns_in_row - 1

            IF matrix[row][col] < minValue
                minValue ← matrix[row][col]
            END IF

            IF matrix[row][col] > maxValue
                maxValue ← matrix[row][col]
            END IF

        END FOR
    END FOR

    RETURN (minValue, maxValue)

END FUNCTION

```

### Code
```js
function FindMaxAndMinElementsInMatrix(mat){

    let Max = -Infinity;
    let Min = Infinity;

    // EDGE CASES
    if(mat.length === 0 || 
        mat[0].length === 0) return "EMPTY MATRIX";

    if(mat.length === 1){
        Min = mat[0][0];
        Max = mat[0][0];
    }

    for(let i=0; i<mat.length; i++){
        for(let j=0; j<mat[i].length; j++){
            if(mat[i][j] > Max) {
                Max = mat[i][j];
            }
            if(mat[i][j] < Min) {
                Min = mat[i][j];
            }
        }
    }

    return {
        MinimumElement : Min,
        MaximumElement : Max 
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