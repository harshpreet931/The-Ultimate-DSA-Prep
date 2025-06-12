# Longest Consecutive Sequence (LC 128)

**Link:** [https://leetcode.com/problems/longest-consecutive-sequence/](https://leetcode.com/problems/longest-consecutive-sequence/)

**Difficulty:** Medium

**Hint/Core Idea:**
The goal is to find the length of the longest consecutive elements sequence in O(n) time.

1.  **Convert to Set:** Add all numbers from `nums` into a set (`num_set`) for O(1) average time lookups.
2.  Initialize `max_length = 0`.
3.  Iterate through each `num` in `num_set` (or original `nums` array, but checking `num_set` is cleaner):
    -   **Check for Start of a Sequence:** If `(num - 1)` is NOT in `num_set`, then `num` is a potential start of a new consecutive sequence.
    -   If it's a start:
        -   Initialize `current_num = num` and `current_length = 1`.
        -   While `(current_num + 1)` IS in `num_set`:
            -   Increment `current_num`.
            -   Increment `current_length`.
        -   Update `max_length = max(max_length, current_length)`.
4.  Return `max_length`.

This approach ensures that we only build sequences starting from their actual first element, avoiding redundant checks and achieving O(n) overall complexity because each number is visited at most twice (once in the outer loop, once in the inner `while` loop if it's part of a sequence being counted).

**Tags:** `Array`, `Hash Table`, `Set`, `Union Find` (less common for this specific O(n) approach)

---
## Problem Description (from LeetCode)

<!-- Placeholder for the full problem description from LeetCode.
     Copy the problem description here from the LeetCode page for easy reference.
     Example: Given an unsorted array of integers nums, return the length of the longest consecutive elements sequence. You must write an algorithm that runs in O(n) time.
-->


## Solution Skeleton (Python)

```python
from typing import List

class Solution:
    def longestConsecutive(self, nums: List[int]) -> int:
        # TODO: Implement solution
        pass

# Example Usage (optional, for testing):
# sol = Solution()
# print(sol.longestConsecutive([100,4,200,1,3,2])) # Expected: 4 (sequence 1,2,3,4)
# print(sol.longestConsecutive([0,3,7,2,5,8,4,6,0,1])) # Expected: 9 (sequence 0,1,2,3,4,5,6,7,8)
# print(sol.longestConsecutive([])) # Expected: 0
# print(sol.longestConsecutive([1,2,0,1])) # Expected: 3 (sequence 0,1,2)
```
---
