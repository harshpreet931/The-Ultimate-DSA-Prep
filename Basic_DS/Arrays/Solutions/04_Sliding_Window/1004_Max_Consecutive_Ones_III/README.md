# Max Consecutive Ones III (LC 1004)

**Link:** [https://leetcode.com/problems/max-consecutive-ones-iii/](https://leetcode.com/problems/max-consecutive-ones-iii/)

**Difficulty:** Medium

**Hint/Core Idea:**
Sliding window approach. We want to find the longest subarray that contains at most `k` zeros.
- `window_start = 0`, `max_length = 0`, `zero_count = 0`.
- Expand window (increment `window_end`):
    - If `nums[window_end] == 0`, increment `zero_count`.
- While `zero_count > k` (window is invalid):
    - If `nums[window_start] == 0`, decrement `zero_count`.
    - Increment `window_start` (shrink window from left).
- Update `max_length = max(max_length, window_end - window_start + 1)`.

**Tags:** `Array`, `Sliding Window`, `Binary Search`, `Prefix Sum`

---
## Problem Description (from LeetCode)

<!-- Placeholder for the full problem description from LeetCode.
     Copy the problem description here from the LeetCode page for easy reference.
     Example: Given a binary array nums and an integer k, return the maximum number of consecutive 1's in the array if you can flip at most k 0's.
-->


## Solution Skeleton (Python)

```python
from typing import List

class Solution:
    def longestOnes(self, nums: List[int], k: int) -> int:
        # TODO: Implement solution
        pass

# Example Usage (optional, for testing):
# sol = Solution()
# print(sol.longestOnes([1,1,1,0,0,0,1,1,1,1,0], 2)) # Expected: 6 (from index 0 to 5 or 6 to 10 after flips)
# print(sol.longestOnes([0,0,1,1,0,0,1,1,1,0,1,1,0,0,0,1,1,1,1], 3)) # Expected: 10
```
---
