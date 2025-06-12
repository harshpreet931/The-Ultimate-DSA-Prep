# Subarray Sum Equals K (LC 560)

**Link:** [https://leetcode.com/problems/subarray-sum-equals-k/](https://leetcode.com/problems/subarray-sum-equals-k/)

**Difficulty:** Medium

**Hint/Core Idea:**
Classic application of prefix sums combined with a hash map.
The goal is to find pairs `(i, j)` such that `sum(nums[i..j]) == k`.
This can be rewritten using prefix sums: `prefix_sum[j+1] - prefix_sum[i] == k`.
Rearranging, we get `prefix_sum[j+1] - k == prefix_sum[i]`.

Iterate through the array, calculating the `current_prefix_sum`.
For each `current_prefix_sum`, we check if `(current_prefix_sum - k)` exists as a key in our hash map (`prefix_sum_counts`).
- The hash map stores `prefix_sum_value: count_of_occurrences`.
- Initialize `count = 0`, `current_prefix_sum = 0`, and `prefix_sum_counts = {0: 1}` (to handle subarrays starting from index 0).
- For each number `num` in `nums`:
    - `current_prefix_sum += num`
    - If `(current_prefix_sum - k)` is in `prefix_sum_counts`, then `count += prefix_sum_counts[current_prefix_sum - k]`.
    - Increment `prefix_sum_counts[current_prefix_sum]` (or initialize if not present).

**Tags:** `Array`, `Prefix Sum`, `Hash Table`

---
## Problem Description (from LeetCode)

<!-- Placeholder for the full problem description from LeetCode.
     Copy the problem description here from the LeetCode page for easy reference.
     Example: Given an array of integers nums and an integer k, return the total number of subarrays whose sum equals to k.
-->


## Solution Skeleton (Python)

```python
from typing import List
from collections import defaultdict

class Solution:
    def subarraySum(self, nums: List[int], k: int) -> int:
        # TODO: Implement solution
        pass

# Example Usage (optional, for testing):
# sol = Solution()
# print(sol.subarraySum([1,1,1], 2))         # Expected: 2 ([1,1] starting at index 0, [1,1] starting at index 1)
# print(sol.subarraySum([1,2,3], 3))         # Expected: 2 ([1,2], [3])
# print(sol.subarraySum([1,-1,5,-2,3], 3))   # Expected: 2 ([1,-1,5,-2], [5,-2])
# print(sol.subarraySum([1], 0))             # Expected: 0
# print(sol.subarraySum([-1,-1,1], 0))       # Expected: 1 ([-1,1])
```
---
