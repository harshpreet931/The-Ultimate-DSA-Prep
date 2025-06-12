# Search a 2D Matrix (LC 74)

**Link:** [https://leetcode.com/problems/search-a-2d-matrix/](https://leetcode.com/problems/search-a-2d-matrix/)

**Difficulty:** Medium

**Hint/Core Idea:**
The matrix has two key properties:
1.  Integers in each row are sorted from left to right.
2.  The first integer of each row is greater than the last integer of the previous row.
This means the entire matrix can be treated as a single sorted list.

**Approach 1: Binary Search on the "Flattened" Matrix**
- Treat the `m x n` matrix as a sorted array of `m * n` elements.
- Perform a standard binary search.
- To convert a 1D index `mid` (from binary search) to 2D matrix coordinates `(row, col)`:
    - `row = mid // n` (where `n` is number of columns)
    - `col = mid % n`
- Compare `matrix[row][col]` with the `target`.

**Approach 2: Two-Step Binary Search**
1.  **Binary Search for the Row:**
    - Perform binary search on the first element of each row to find which row *could* contain the target.
    - If `matrix[mid_row][0] <= target` and (if `mid_row` is not the last row) `target < matrix[mid_row+1][0]`, then this `mid_row` is the candidate row. Or if `target >= matrix[last_row][0]`, then `last_row` is the candidate.
2.  **Binary Search within the Row:**
    - Once the candidate row is identified, perform a standard binary search for the `target` within that row.

**Tags:** `Array`, `Matrix`, `Binary Search`

---
## Problem Description (from LeetCode)

<!-- Placeholder for the full problem description from LeetCode.
     Copy the problem description here from the LeetCode page for easy reference.
     Example: You are given an m x n integer matrix with the following two properties: Each row is sorted in non-decreasing order. The first integer of each row is greater than the last integer of the previous row. Given an integer target, return true if target is in matrix or false otherwise. You must write a solution in O(log(m * n)) time complexity.
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
# print(sol.searchMatrix([[1,3,5,7],[10,11,16,20],[23,30,34,60]], 3))  # Expected: True
# print(sol.searchMatrix([[1,3,5,7],[10,11,16,20],[23,30,34,60]], 13)) # Expected: False
# print(sol.searchMatrix([[1]], 1)) # Expected: True
# print(sol.searchMatrix([[1]], 0)) # Expected: False
```
---
