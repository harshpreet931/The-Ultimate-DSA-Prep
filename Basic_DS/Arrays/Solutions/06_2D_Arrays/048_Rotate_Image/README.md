# Rotate Image (LC 48)

**Link:** [https://leetcode.com/problems/rotate-image/](https://leetcode.com/problems/rotate-image/)

**Difficulty:** Medium

**Hint/Core Idea:**
To rotate an N x N matrix 90 degrees clockwise in-place:
1.  **Transpose the matrix:** Swap `matrix[i][j]` with `matrix[j][i]` for all `i < j`.
    - Iterate `i` from `0` to `N-1`.
    - Iterate `j` from `i+1` to `N-1`. (Only upper or lower triangle to avoid double swaps)
    - Swap `matrix[i][j]` and `matrix[j][i]`.
2.  **Reflect (Reverse) each row:** For each row, reverse its elements.
    - Iterate `i` from `0` to `N-1` (for each row).
    - Reverse `matrix[i]` (e.g., using two pointers, one from start of row, one from end).

**Tags:** `Array`, `Matrix`, `In-Place Modification`, `Math`

---
## Problem Description (from LeetCode)

<!-- Placeholder for the full problem description from LeetCode.
     Copy the problem description here from the LeetCode page for easy reference.
     Example: You are given an n x n 2D matrix representing an image, rotate the image by 90 degrees (clockwise). You have to rotate the image in-place, which means you have to modify the input 2D matrix directly. DO NOT allocate another 2D matrix and do the rotation.
-->


## Solution Skeleton (Python)

```python
from typing import List

class Solution:
    def rotate(self, matrix: List[List[int]]) -> None:
        """
        Do not return anything, modify matrix in-place instead.
        """
        # TODO: Implement solution
        pass

# Example Usage (optional, for testing):
# sol = Solution()
# matrix1 = [[1,2,3],[4,5,6],[7,8,9]]
# sol.rotate(matrix1)
# print(matrix1) 
# # Expected: [[7,4,1],[8,5,2],[9,6,3]]

# matrix2 = [[5,1,9,11],[2,4,8,10],[13,3,6,7],[15,14,12,16]]
# sol.rotate(matrix2)
# print(matrix2)
# # Expected: [[15,13,2,5],[14,3,4,1],[12,6,8,9],[16,7,10,11]]
```
---
