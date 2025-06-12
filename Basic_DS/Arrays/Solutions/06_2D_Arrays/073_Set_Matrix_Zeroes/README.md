# Set Matrix Zeroes (LC 73)

**Link:** [https://leetcode.com/problems/set-matrix-zeroes/](https://leetcode.com/problems/set-matrix-zeroes/)

**Difficulty:** Medium

**Hint/Core Idea:**
In-place modification. The main challenge is to avoid zeroing out rows/columns based on cells that were themselves turned to zero as part of the process.

**O(1) Space (using first row/column as markers):**
1.  Determine if the first row and first column need to be zeroed out. Store this information in boolean variables (e.g., `first_row_zero`, `first_col_zero`).
    - Iterate through the first row. If any element is 0, `first_row_zero = true`.
    - Iterate through the first column. If any element is 0, `first_col_zero = true`.
2.  Use the first row and first column of the matrix itself as markers.
    - Iterate through the rest of the matrix (from `matrix[1][1]` onwards).
    - If `matrix[i][j] == 0`, then set `matrix[i][0] = 0` and `matrix[0][j] = 0`.
3.  Zero out rows and columns based on markers in the first row/column.
    - Iterate from `i = 1` to `rows-1`. If `matrix[i][0] == 0`, zero out the entire `i`-th row.
    - Iterate from `j = 1` to `cols-1`. If `matrix[0][j] == 0`, zero out the entire `j`-th column.
4.  Finally, if `first_row_zero` is true, zero out the first row.
5.  If `first_col_zero` is true, zero out the first column.

**O(m+n) Space (using extra arrays):**
1. Create two boolean arrays: `zero_rows[m]` and `zero_cols[n]`.
2. Iterate through the matrix. If `matrix[i][j] == 0`, set `zero_rows[i] = true` and `zero_cols[j] = true`.
3. Iterate through the matrix again. If `zero_rows[i]` is true or `zero_cols[j]` is true, set `matrix[i][j] = 0`.

**Tags:** `Array`, `Matrix`, `In-Place Modification`

---
## Problem Description (from LeetCode)

<!-- Placeholder for the full problem description from LeetCode.
     Copy the problem description here from the LeetCode page for easy reference.
     Example: Given an m x n integer matrix, if an element is 0, set its entire row and column to 0's. You must do it in-place.
-->


## Solution Skeleton (Python)

```python
from typing import List

class Solution:
    def setZeroes(self, matrix: List[List[int]]) -> None:
        """
        Do not return anything, modify matrix in-place instead.
        """
        # TODO: Implement solution
        pass

# Example Usage (optional, for testing):
# sol = Solution()
# matrix1 = [[1,1,1],[1,0,1],[1,1,1]]
# sol.setZeroes(matrix1)
# print(matrix1) # Expected: [[1,0,1],[0,0,0],[1,0,1]]

# matrix2 = [[0,1,2,0],[3,4,5,2],[1,3,1,5]]
# sol.setZeroes(matrix2)
# print(matrix2) # Expected: [[0,0,0,0],[0,4,5,0],[0,3,1,0]]
```
---
