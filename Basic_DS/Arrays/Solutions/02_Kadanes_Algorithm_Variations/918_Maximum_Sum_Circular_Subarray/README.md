# Maximum Sum Circular Subarray (LC 918)

**Link:** [https://leetcode.com/problems/maximum-sum-circular-subarray/](https://leetcode.com/problems/maximum-sum-circular-subarray/)

**Difficulty:** Medium

**Hint/Core Idea:**
Combines Kadane's with total sum and min subarray sum concepts.
The answer is either the max subarray sum (Kadane's) or (total sum - min subarray sum).
Handle the case where all numbers are negative separately (Kadane's result will be the answer).

**Tags:** `Array`, `Dynamic Programming`, `Kadane's Algorithm`

---
## Problem Description (from LeetCode)

<!-- Placeholder for the full problem description from LeetCode.
     Copy the problem description here from the LeetCode page for easy reference.
     Example: Given a circular integer array nums of length n, return the maximum possible sum of a non-empty subarray of nums.
-->


## Solution Skeleton (Python)

```python
from typing import List

class Solution:
    def maxSubarraySumCircular(self, nums: List[int]) -> int:
        # TODO: Implement solution
        pass

# Example Usage (optional, for testing):
# sol = Solution()
# print(sol.maxSubarraySumCircular([1,-2,3,-2]))       # Expected: 3
# print(sol.maxSubarraySumCircular([5,-3,5]))          # Expected: 10
# print(sol.maxSubarraySumCircular([3,-1,2,-1]))       # Expected: 4
# print(sol.maxSubarraySumCircular([3,-2,2,-3]))       # Expected: 3
# print(sol.maxSubarraySumCircular([-2,-3,-1]))      # Expected: -1
```
---
