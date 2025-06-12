# Trapping Rain Water (LC 42)

**Link:** [https://leetcode.com/problems/trapping-rain-water/](https://leetcode.com/problems/trapping-rain-water/)

**Difficulty:** Hard

**Hint/Core Idea:**
Can be solved with two pointers, dynamic programming, or stack. The two-pointer approach is elegant:
Maintain `left_max` and `right_max`.
If `height[left] < height[right]`:
  If `height[left] >= left_max`, update `left_max`.
  Else, `water += left_max - height[left]`.
  Increment `left`.
Else:
  If `height[right] >= right_max`, update `right_max`.
  Else, `water += right_max - height[right]`.
  Decrement `right`.

**Tags:** `Array`, `Two Pointers`, `Dynamic Programming`, `Stack`, `Monotonic Stack`

---
## Problem Description (from LeetCode)

<!-- Placeholder for the full problem description from LeetCode.
     Copy the problem description here from the LeetCode page for easy reference.
     Example: Given n non-negative integers representing an elevation map where the width of each bar is 1, compute how much water it can trap after raining.
-->


## Solution Skeleton (Python)

```python
from typing import List

class Solution:
    def trap(self, height: List[int]) -> int:
        # TODO: Implement solution
        pass

# Example Usage (optional, for testing):
# sol = Solution()
# print(sol.trap([0,1,0,2,1,0,1,3,2,1,2,1])) # Expected: 6
# print(sol.trap([4,2,0,3,2,5]))             # Expected: 9
```
---
