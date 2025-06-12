# Spiral Matrix (LC 54)

**Link:** [https://leetcode.com/problems/spiral-matrix/](https://leetcode.com/problems/spiral-matrix/)

**Difficulty:** Medium

**Hint/Core Idea:**
Traverse the matrix layer by layer, simulating the spiral path.
Maintain four boundary pointers: `top`, `bottom`, `left`, `right`.
Initialize `result = []`.
Loop as long as `top <= bottom` and `left <= right`:
1.  **Traverse Right:** From `left` to `right` along the `top` row. Add `matrix[top][j]` to `result`. Increment `top`.
2.  **Traverse Down:** From `top` to `bottom` along the `right` column. Add `matrix[i][right]` to `result`. Decrement `right`.
3.  **Traverse Left (if top <= bottom):** From `right` down to `left` along the `bottom` row. Add `matrix[bottom][j]` to `result`. Decrement `bottom`. (Check `top <= bottom` to handle single row matrices after top increment).
4.  **Traverse Up (if left <= right):** From `bottom` down to `top` along the `left` column. Add `matrix[i][left]` to `result`. Increment `left`. (Check `left <= right` to handle single column matrices after right decrement).

Be careful with edge cases like single row/column matrices or when the layers meet. The checks `top <= bottom` and `left <= right` before traversing left and up are crucial.

**Tags:** `Array`, `Matrix`, `Simulation`

---
## Problem Description (from LeetCode)

<!-- Placeholder for the full problem description from LeetCode.
     Copy the problem description here from the LeetCode page for easy reference.
     Example: Given an m x n matrix, return all elements of the matrix in spiral order.
-->


## Solution Skeleton (Python)

```python
from typing import List

class Solution:
    def spiralOrder(self, matrix: List[List[int]]) -> List[int]:
        # TODO: Implement solution
        pass

# Example Usage (optional, for testing):
# sol = Solution()
# print(sol.spiralOrder([[1,2,3],[4,5,6],[7,8,9]])) 
# # Expected: [1,2,3,6,9,8,7,4,5]

# print(sol.spiralOrder([[1,2,3,4],[5,6,7,8],[9,10,11,12]]))
# # Expected: [1,2,3,4,8,12,11,10,9,5,6,7]

# print(sol.spiralOrder([[7],[9],[6]]))
# # Expected: [7,9,6]
```
---
