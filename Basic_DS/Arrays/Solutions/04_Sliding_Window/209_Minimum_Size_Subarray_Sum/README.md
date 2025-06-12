# Minimum Size Subarray Sum (LC 209)

**Link:** [https://leetcode.com/problems/minimum-size-subarray-sum/](https://leetcode.com/problems/minimum-size-subarray-sum/)

**Difficulty:** Medium

**Hint/Core Idea:**
Variable-size sliding window.
- Initialize `min_length = float('inf')`, `current_sum = 0`, `window_start = 0`.
- Iterate with `window_end` through the array, adding `nums[window_end]` to `current_sum`.
- While `current_sum >= target`:
    - Update `min_length = min(min_length, window_end - window_start + 1)`.
    - Subtract `nums[window_start]` from `current_sum` (shrink window from left).
    - Increment `window_start`.
- If `min_length` remains `float('inf')`, return 0, else return `min_length`.

**Tags:** `Array`, `Sliding Window`, `Binary Search`, `Prefix Sum`

---
## Problem Description (from LeetCode)

<!-- Placeholder for the full problem description from LeetCode.
     Copy the problem description here from the LeetCode page for easy reference.
     Example: Given an array of positive integers nums and a positive integer target, return the minimal length of a subarray whose sum is greater than or equal to target. If there is no such subarray, return 0 instead.
-->


## Solution Skeleton (Python)

```python
from typing import List
import math

class Solution:
    def minSubArrayLen(self, target: int, nums: List[int]) -> int:
        # TODO: Implement solution
        pass

# Example Usage (optional, for testing):
# sol = Solution()
# print(sol.minSubArrayLen(7, [2,3,1,2,4,3])) # Expected: 2 (from [4,3])
# print(sol.minSubArrayLen(4, [1,4,4]))       # Expected: 1 (from [4])
# print(sol.minSubArrayLen(11, [1,1,1,1,1,1,1,1])) # Expected: 0
```
---
