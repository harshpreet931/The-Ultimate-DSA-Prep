# Range Sum Query - Immutable (LC 303)

**Link:** [https://leetcode.com/problems/range-sum-query-immutable/](https://leetcode.com/problems/range-sum-query-immutable/)

**Difficulty:** Easy

**Hint/Core Idea:**
Introduction to Prefix Sum.
Precompute an array `prefix_sum` where `prefix_sum[i]` stores the sum of `nums[0...i-1]`.
`prefix_sum[0]` can be 0 (representing sum before any element).
Then, `sumRange(left, right)` is `prefix_sum[right + 1] - prefix_sum[left]`.

**Tags:** `Array`, `Prefix Sum`, `Design`

---
## Problem Description (from LeetCode)

<!-- Placeholder for the full problem description from LeetCode.
     Copy the problem description here from the LeetCode page for easy reference.
     Example: Given an integer array nums, handle multiple queries of the following type: Calculate the sum of the elements of nums between indices left and right inclusive where left <= right.
-->


## Solution Skeleton (Python)

```python
from typing import List

class NumArray:

    def __init__(self, nums: List[int]):
        # TODO: Initialize prefix sum array
        self.prefix_sum = [0] * (len(nums) + 1)
        for i in range(len(nums)):
            self.prefix_sum[i+1] = self.prefix_sum[i] + nums[i]

    def sumRange(self, left: int, right: int) -> int:
        # TODO: Calculate sum using prefix sum array
        if left < 0 or right >= len(self.prefix_sum) -1 or left > right :
             # Or handle error appropriately based on constraints
            return 0 # Should ideally raise error or match problem spec for invalid inputs
        return self.prefix_sum[right + 1] - self.prefix_sum[left]


# Example Usage (optional, for testing):
# numArray = NumArray([-2, 0, 3, -5, 2, -1])
# print(numArray.sumRange(0, 2)) # return (-2) + 0 + 3 = 1
# print(numArray.sumRange(2, 5)) # return 3 + (-5) + 2 + (-1) = -1
# print(numArray.sumRange(0, 5)) # return (-2) + 0 + 3 + (-5) + 2 + (-1) = -3
```
---
