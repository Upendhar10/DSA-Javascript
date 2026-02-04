## Optimal Approach

### Intuition

Matrix multiplication is **row × column pairing**.

Think of it like this:

* Each **row of mat1** represents a set of values
* Each **column of mat2** represents another set of values
* To compute **one cell** in the result matrix:

  * Take the row from `mat1`
  * Take the column from `mat2`
  * Multiply corresponding elements
  * Add them up (dot product)

**Example idea :**

To compute:

```
result[i][j]
```

We should do:

```
(mat1[i][0] * mat2[0][j]) +
(mat1[i][1] * mat2[1][j]) +
...
(mat1[i][c1-1] * mat2[c1-1][j])
```

So:

* One **cell** → needs a loop
* One **row** → needs another loop
* Whole matrix → needs the outer loop

That’s why we naturally end up with **3 loops**.

**Conditions to remember :**

* `c1 === r2` → otherwise multiplication is impossible
* Result matrix size → **`r1 × c2`**

### Pseudo Code

```
FUNCTION MultiplyTwoMatrices(mat1, mat2, r1, c1, r2, c2)

    IF c1 ≠ r2
        RETURN "Invalid Matrices"

    IF r1 = 0 OR r2 = 0
        RETURN "Empty Matrices"

    result ← empty matrix

    FOR i FROM 0 TO r1 - 1
        row ← empty list

        FOR j FROM 0 TO c2 - 1
            sum ← 0

            FOR k FROM 0 TO c1 - 1
                sum ← sum + (mat1[i][k] × mat2[k][j])
            END FOR

            ADD sum TO row
        END FOR

        ADD row TO result
    END FOR

    RETURN result
END FUNCTION

```

### Code
```js

function MultiplyTwoMatrices(mat1, mat2, r1, c1, r2, c2) {

    // VALIDATION
    if (c1 !== r2) return "Invalid Matrices";
    if (r1 === 0 || r2 === 0) return "Empty Matrices";

    let result = []; // size: r1 x c2

    for (let i = 0; i < r1; i++) {
        let row = [];

        for (let j = 0; j < c2; j++) {
            let sum = 0;

            for (let k = 0; k < c1; k++) {
                sum += mat1[i][k] * mat2[k][j];
            }

            row.push(sum);
        }

        result.push(row);
    }

    return result;
}
```

### Algorithmic Analysis

**Time Complexity** : O (n ^ 3)
```
O(r1 × c2 × c1)
where,
- Outer loop → r1
- Inner loop → c2
- Deep loop → c1

So, for a (n x n) matrices : O(n ^ 3)
```

**Space Complexity** : O(r1 × c2)

## Can This Be Optimized Further?

###  Algorithmically (General Case)

**No**, not in the general sense.

- Matrix multiplication works by taking the dot product of each row of the first matrix with each column of the second matrix. 

- This naturally leads to three nested loops, resulting in `O(n³)` time complexity, which is optimal for standard matrix multiplication.

* Standard matrix multiplication **must** touch each row–column pair
* Triple loop is unavoidable for generic matrices