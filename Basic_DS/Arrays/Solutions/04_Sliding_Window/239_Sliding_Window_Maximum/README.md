# Sliding Window Maximum (LC 239)

**Link:** [https://leetcode.com/problems/sliding-window-maximum/](https://leetcode.com/problems/sliding-window-maximum/)

**Difficulty:** Hard

**Hint/Core Idea:**
Use a monotonic decreasing deque (double-ended queue) to store indices of elements in the current window. The deque stores indices of elements in decreasing order of their values.
1. Initialize `result = []` and `deque = collections.deque()`.
2. Iterate `i` from `0` to `n-1`:
   a. **Remove elements from left of deque that are out of window:**
      If `deque` is not empty and `deque[0] == i - k`, pop from left.
   b. **Maintain monotonic decreasing property:**
      While `deque` is not empty and `nums[deque[-1]] < nums[i]`, pop from right.
   c. **Add current element's index to deque:**
      Append `i` to `deque`.
   d. **Add max to result (once window is full):**
      If `i >= k - 1`, append `nums[deque[0]]` to `result`.
Return `result`.

**Tags:** `Array`, `Sliding Window`, `Queue`, `Monotonic Queue`, `Deque`

---
## Problem Description (from LeetCode)

<!-- Placeholder for the full problem description from LeetCode.
     Copy the problem description here from the LeetCode page for easy reference.
     Example: You are given an array of integers nums, there is a sliding window of size k moving from the very left of the array to the very right. You can only see the k numbers in the window. Each time the sliding window moves right by one position. Return the max sliding window.
-->


## Solution Skeleton (Python)

```python
from typing import List
import collections

class Solution:
    def maxSlidingWindow(self, nums: List[int], k: int) -> List[int]:
        # TODO: Implement solution
        pass

# Example Usage (optional, for testing):
# sol = Solution()
# print(sol.maxSlidingWindow([1,3,-1,-3,5,3,6,7], 3)) # Expected: [3,3,5,5,6,7]
# print(sol.maxSlidingWindow([1], 1))                # Expected: [1]
# print(sol.maxSlidingWindow([1,-1], 1))               # Expected: [1,-1]
# print(sol.maxSlidingWindow([9,11], 2))             # Expected: [11]
# print(sol.maxSlidingWindow([4,-2], 2))             # Expected: [4]
```
---
