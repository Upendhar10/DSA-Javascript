## Optimal Approach

### Intuition

- If Transpose of a matrix is equal to given matrix, then it is symmetric matrix.
- Only Square matrices can form a Symmetric Matrix.
    - no.of rows === no.of columns

**NOTE :**
- We start `j` from `i + 1` to avoid redundant comparisons.
- Because symmetry requires checking `matrix[i][j] === matrix[j][i]`, checking both `(i, j)` and `(j, i)` would duplicate work.
- This approach ensures we only traverse the upper triangle of the matrix, skipping diagonal elements and reducing unnecessary computations.

### Pseudo Code

```
FUNCTION isSymmetricMatrix(matrix){

    let rows = matrix.length
    let cols = matrix[0].length

    if rows === 0 :
    return true;

    if rows != columns:
    return false

    for i from 0 to n-1:
        for j from i+1 to n-1:
            if matrix[i][j] != matrix[j][i]:
                return false

    return true
}

```

### Code

```js
function isSymmetricMatrix(matrix){

    // if no.of rows === no.of columns
    let rows = matrix.length;
    let cols = matrix[0].length;

    if(matrix.length === 0) return true;

    if(rows !== cols) return false;

    for(let i=0; i<matrix.length; i++){
        for(let j=i+1; j<matrix[i].length; j++){
            if(matrix[i][j] !== matrix[j][i]){
                return false;
            }
        }
    }
    return true;
}
```

### Algorithmic Analysis

**Time Complexity** : O(n^2)

**Space Complexity** : O(1)