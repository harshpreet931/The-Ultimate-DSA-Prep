# Sort Colors (LC 75)

**Link:** [https://leetcode.com/problems/sort-colors/](https://leetcode.com/problems/sort-colors/)

**Difficulty:** Medium

**Hint/Core Idea:**
Dutch National Flag problem using three pointers (low, mid, high).
- `low`: boundary for 0s.
- `mid`: current element being considered.
- `high`: boundary for 2s.

Iterate with `mid`:
- If `nums[mid] == 0`: swap `nums[low]` and `nums[mid]`, increment `low` and `mid`.
- If `nums[mid] == 1`: increment `mid`.
- If `nums[mid] == 2`: swap `nums[mid]` and `nums[high]`, decrement `high`. (Do not increment `mid` here as the swapped element from `high` needs to be processed).

**Tags:** `Array`, `Two Pointers`, `Sorting`

---
## Problem Description (from LeetCode)

<!-- Placeholder for the full problem description from LeetCode.
     Copy the problem description here from the LeetCode page for easy reference.
     Example: Given an array nums with n objects colored red, white, or blue, sort them in-place so that objects of the same color are adjacent, with the colors in the order red, white, and blue. We will use the integers 0, 1, and 2 to represent the color red, white, and blue, respectively. You must solve this problem without using the library's sort function.
-->


## Solution Skeleton (Python)

```python
from typing import List

class Solution:
    def sortColors(self, nums: List[int]) -> None:
        """
        Do not return anything, modify nums in-place instead.
        """
        # TODO: Implement solution
        pass

# Example Usage (optional, for testing):
# sol = Solution()
# arr1 = [2,0,2,1,1,0]
# sol.sortColors(arr1)
# print(arr1) # Expected: [0,0,1,1,2,2]

# arr2 = [2,0,1]
# sol.sortColors(arr2)
# print(arr2) # Expected: [0,1,2]
```
---
