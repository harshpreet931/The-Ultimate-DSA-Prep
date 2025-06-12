# Search a 2D Matrix II (LC 240)

**Link:** [https://leetcode.com/problems/search-a-2d-matrix-ii/](https://leetcode.com/problems/search-a-2d-matrix-ii/)

**Difficulty:** Medium

**Hint/Core Idea:**
The matrix has integers sorted in non-decreasing order in each row (left to right) and each column (top to bottom). This structure is different from LC 74 (Search a 2D Matrix).

**Efficient Search Approach (O(m+n) time):**
1.  Start the search from either the top-right corner (`row = 0, col = n-1`) or the bottom-left corner (`row = m-1, col = 0`). Let's use top-right.
2.  Loop while `row < m` and `col >= 0`:
    -   Let `current_element = matrix[row][col]`.
    -   If `current_element == target`, return `True`.
    -   If `current_element > target`: The target must be to the left (if it exists in this row), so decrement `col`.
    -   If `current_element < target`: The target must be downwards (if it exists in this column), so increment `row`.
3.  If the loop finishes without finding the target, return `False`.

This approach works because at each step, we eliminate either a row or a column.

**Tags:** `Array`, `Matrix`, `Binary Search`, `Divide and Conquer`

---
## Problem Description (from LeetCode)

<!-- Placeholder for the full problem description from LeetCode.
     Copy the problem description here from the LeetCode page for easy reference.
     Example: Write an efficient algorithm that searches for a value target in an m x n integer matrix. This matrix has the following properties: Integers in each row are sorted in ascending from left to right. Integers in each column are sorted in ascending from top to bottom.
-->


## Solution Skeleton (Python)

```python
from typing import List

class Solution:
    def searchMatrix(self, matrix: List[List[int]], target: int) -> bool:
        # TODO: Implement solution
        pass

# Example Usage (optional, for testing):
# sol = Solution()
# matrix_ex1 = [[1,4,7,11,15],[2,5,8,12,19],[3,6,9,16,22],[10,13,14,17,24],[18,21,23,26,30]]
# print(sol.searchMatrix(matrix_ex1, 5))  # Expected: True
# print(sol.searchMatrix(matrix_ex1, 20)) # Expected: False

# matrix_ex2 = [[-5]]
# print(sol.searchMatrix(matrix_ex2, -5)) # Expected: True
```
---
