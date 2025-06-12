# 3Sum (LC 15)

**Link:** [https://leetcode.com/problems/3sum/](https://leetcode.com/problems/3sum/)

**Difficulty:** Medium

**Hint/Core Idea:**
Combines sorting with two pointers (fix one element, find two others). Careful with duplicates.

**Tags:** `Array`, `Two Pointers`, `Sorting`

---
## Problem Description (from LeetCode)

<!-- Placeholder for the full problem description from LeetCode.
     Copy the problem description here from the LeetCode page for easy reference.
     Example: Given an integer array nums, return all the triplets [nums[i], nums[j], nums[k]] such that i != j, i != k, and j != k, and nums[i] + nums[j] + nums[k] == 0. Notice that the solution set must not contain duplicate triplets.
-->


## Solution Skeleton (Python)

```python
from typing import List

class Solution:
    def threeSum(self, nums: List[int]) -> List[List[int]]:
        # TODO: Implement solution
        pass

# Example Usage (optional, for testing):
# sol = Solution()
# print(sol.threeSum([-1,0,1,2,-1,-4])) # Expected: [[-1,-1,2],[-1,0,1]] (order of triplets and elements within triplets might vary)
# print(sol.threeSum([0,1,1]))         # Expected: []
# print(sol.threeSum([0,0,0]))         # Expected: [[0,0,0]]
```
---
