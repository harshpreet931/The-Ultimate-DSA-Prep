# Maximum Product Subarray (LC 152)

**Link:** [https://leetcode.com/problems/maximum-product-subarray/](https://leetcode.com/problems/maximum-product-subarray/)

**Difficulty:** Medium

**Hint/Core Idea:**
Variation of Kadane's, need to track min product too due to negatives.

**Tags:** `Array`, `Dynamic Programming`

---
## Problem Description (from LeetCode)

<!-- Placeholder for the full problem description from LeetCode.
     Copy the problem description here from the LeetCode page for easy reference.
     Example: Given an integer array nums, find a subarray that has the largest product, and return the product.
-->


## Solution Skeleton (Python)

```python
from typing import List

class Solution:
    def maxProduct(self, nums: List[int]) -> int:
        # TODO: Implement solution
        pass

# Example Usage (optional, for testing):
# sol = Solution()
# print(sol.maxProduct([2,3,-2,4]))    # Expected: 6 (from [2,3])
# print(sol.maxProduct([-2,0,-1]))   # Expected: 0
# print(sol.maxProduct([-2,3,-4]))   # Expected: 24 (from [-2,3,-4])
# print(sol.maxProduct([0,2]))        # Expected: 2
# print(sol.maxProduct([-3,-1,-1]))   # Expected: 3 (from [-1,-1] or -3 * -1)
```
---
