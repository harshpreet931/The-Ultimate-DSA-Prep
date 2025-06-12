# 4Sum (LC 18)

**Link:** [https://leetcode.com/problems/4sum/](https://leetcode.com/problems/4sum/)

**Difficulty:** Medium

**Hint/Core Idea:**
Extension of 3Sum. Sort the array first.
Use two outer loops to fix the first two numbers (`i` and `j`).
Then use a two-pointer approach (left, right) for the remaining part of the array to find the other two numbers.
Carefully handle duplicate skipping for all four numbers to avoid duplicate quadruplets in the result.

**Tags:** `Array`, `Two Pointers`, `Sorting`

---
## Problem Description (from LeetCode)

<!-- Placeholder for the full problem description from LeetCode.
     Copy the problem description here from the LeetCode page for easy reference.
     Example: Given an array nums of n integers, return an array of all the unique quadruplets [nums[a], nums[b], nums[c], nums[d]] such that: 0 <= a, b, c, d < n; a, b, c, and d are distinct; and nums[a] + nums[b] + nums[c] + nums[d] == target. You may return the answer in any order.
-->


## Solution Skeleton (Python)

```python
from typing import List

class Solution:
    def fourSum(self, nums: List[int], target: int) -> List[List[int]]:
        # TODO: Implement solution
        pass

# Example Usage (optional, for testing):
# sol = Solution()
# print(sol.fourSum([1,0,-1,0,-2,2], 0))
# # Expected: [[-2,-1,1,2],[-2,0,0,2],[-1,0,0,1]] (order of quadruplets and elements within might vary)

# print(sol.fourSum([2,2,2,2,2], 8))
# # Expected: [[2,2,2,2]]
```
---
