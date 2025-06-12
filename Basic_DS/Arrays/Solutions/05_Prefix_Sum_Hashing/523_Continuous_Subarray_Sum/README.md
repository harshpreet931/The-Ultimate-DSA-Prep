# Continuous Subarray Sum (LC 523)

**Link:** [https://leetcode.com/problems/continuous-subarray-sum/](https://leetcode.com/problems/continuous-subarray-sum/)

**Difficulty:** Medium

**Hint/Core Idea:**
We are looking for a subarray `nums[i..j]` (length at least 2) such that `sum(nums[i..j]) % k == 0`.
This means `sum(nums[i..j]) = n * k` for some integer `n`.
Using prefix sums: `(prefix_sum[j+1] - prefix_sum[i]) % k == 0`.
This implies `prefix_sum[j+1] % k == prefix_sum[i] % k`.

Iterate through the array, calculating `current_prefix_sum`.
Maintain a hash map `remainder_map` that stores `{remainder: index}`.
- Initialize `current_prefix_sum = 0`, `remainder_map = {0: -1}` (to handle cases where the subarray starts from index 0 and its sum is a multiple of k; index -1 ensures length is at least 2 if `current_prefix_sum % k == 0`).
- For each `num` at index `idx` in `nums`:
    - `current_prefix_sum += num`
    - `current_remainder = current_prefix_sum % k` (if `k` is not 0, else `current_remainder = current_prefix_sum`).
    - If `current_remainder` is in `remainder_map`:
        - If `idx - remainder_map[current_remainder] >= 2`, we found a valid subarray. Return `True`.
    - Else (if `current_remainder` not in `remainder_map`):
        - `remainder_map[current_remainder] = idx`.
Special case: if `k == 0`, we are looking for a subarray sum of 0. The modulo logic doesn't apply directly. The general prefix sum logic for `sum == 0` would be needed, or handle as per problem constraints for `k=0`. (LeetCode problem constraints state `k` is positive, so `k=0` is not an issue here).

**Tags:** `Array`, `Prefix Sum`, `Hash Table`, `Math`

---
## Problem Description (from LeetCode)

<!-- Placeholder for the full problem description from LeetCode.
     Copy the problem description here from the LeetCode page for easy reference.
     Example: Given an integer array nums and an integer k, return true if nums has a continuous subarray of size at least two whose elements sum up to a multiple of k, or false otherwise.
-->


## Solution Skeleton (Python)

```python
from typing import List

class Solution:
    def checkSubarraySum(self, nums: List[int], k: int) -> bool:
        # TODO: Implement solution
        pass

# Example Usage (optional, for testing):
# sol = Solution()
# print(sol.checkSubarraySum([23,2,4,6,7], 6))  # Expected: True ([2,4] sum=6, or [23,2,4,6,7] sum=42)
# print(sol.checkSubarraySum([23,2,6,4,7], 6))  # Expected: True ([2,6,4] sum=12, or [6] is not size 2, [23,2,6,4,7] sum=42)
# print(sol.checkSubarraySum([23,2,6,4,7], 13)) # Expected: False
# print(sol.checkSubarraySum([5,0,0,0], 3))    # Expected: True ([0,0])
# print(sol.checkSubarraySum([0,0], 1))        # Expected: True ([0,0])
# print(sol.checkSubarraySum([1,0], 2))        # Expected: False
```
---
