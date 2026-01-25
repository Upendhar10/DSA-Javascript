## Optimal Approach - 1

### Intuition

- In column-wise traversal:
    - Fix a column
- Traverse all rows for that column
    
    That means:
    - Outer loop → columns
    - Inner loop → rows

👉 Access pattern changes to: matrix[row][column]

- So We swap the loop roles, not the indices order.

- For a matrix with:
    `R` rows and `C` columns
```
FOR col from 0 to C - 1
    FOR row from 0 to R - 1
```

### Pseudo Code 

```
FUNCTION printMatrixColumnWise(matrix)

    result ← empty list

    totalRows ← number of rows in matrix
    totalCols ← number of columns in matrix

    FOR col from 0 to totalCols - 1
        column ← empty list

        FOR row from 0 to totalRows - 1
            ADD matrix[row][col] to column
        END FOR

        ADD column to result
    END FOR

    RETURN result
END FUNCTION

```

### Code

```js
function printMatrixColumnWise(matrix) {
    let result = [];

    let totalRows = matrix.length;
    let totalCols = matrix[0].length || 0;

    if (totalCols === 0) return [];

    for (let col = 0; col < totalCols; col++) {
        let column = [];

        for (let row = 0; row < totalRows; row++) {
            column.push(matrix[row][col]);
        }

        result.push(column);
    }

    return result;
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

----

## Optimal Approach - 2

### Intuition

- What if the row have different lengths ?
- For this example :
```
[
  [1, 2, 3],
  [4, 5],
  [6, 7, 8, 9]
]
```
- matrix[row][col] may not exist
- Direct column-wise traversal will break ❌

- So, For jagged matrices, We should compute the maximum column length and check bounds before accessing matrix[row][col].

- In column-wise traversal ( for Jagged Matrix):

- First find the maximum number of columns in any row
- Loop column by column
- For each column, visit only rows that actually have that column index
    
    That means:
    - Outer loop → columns  
    - Inner loop → rows

👉 Access pattern will be: matrix[row][column]

NOTE : Here, We swap the loop roles, not the indices order.

- For a matrix with:
    `R` rows and `C` columns
```
FOR col from 0 to maxCols
    FOR row from 0 to totalRows
```

### Pseudo Code 

```
FUNCTION printMatrixColumnWiseJagged(matrix)

    result ← empty list
    totalRows ← number of rows in matrix

    // Step 1: Find maximum columns
    maxCols ← 0
    FOR row from 0 to totalRows - 1
        IF length of matrix[row] > maxCols
            maxCols ← length of matrix[row]
        END IF
    END FOR

    // Step 2: Column-wise traversal
    FOR col from 0 to maxCols - 1
        column ← empty list

        FOR row from 0 to totalRows - 1
            IF col < length of matrix[row]
                ADD matrix[row][col] to column
            END IF
        END FOR

        ADD column to result
    END FOR

    RETURN result

END FUNCTION

```

### Code

```js
function printMatrixColumnWiseJagged(matrix) {
    let result = [];

    let totalRows = matrix.length;

    // Step 1: find max columns
    let maxCols = 0;
    for (let row = 0; row < totalRows; row++) {
        maxCols = Math.max(maxCols, matrix[row].length);
    }

    // Step 2: column-wise traversal
    for (let col = 0; col < maxCols; col++) {
        let column = [];

        for (let row = 0; row < totalRows; row++) {
            if (col < matrix[row].length) {
                column.push(matrix[row][col]);
            }
        }

        result.push(column);
    }

    return result;
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