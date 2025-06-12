# First Missing Positive (LC 41)

**Link:** [https://leetcode.com/problems/first-missing-positive/](https://leetcode.com/problems/first-missing-positive/)

**Difficulty:** Hard

**Hint/Core Idea:**
Clever in-place hashing using array indices (a variation of cyclic sort). The goal is to place each number `x` at index `x-1` if `1 <= x <= n`.

1.  **Handle out-of-range numbers:** Iterate through the array. If a number is `<= 0` or `> n` (where `n` is the length of the array), it cannot be the first missing positive in the range `[1, n]`. We can ignore them or mark them (e.g., change to `n+1` or some other value outside `[1,n]`). This step is often implicitly handled by the cyclic sort conditions.

2.  **Cyclic Sort / In-place Hashing:**
    - Iterate `i` from `0` to `n-1`:
        - While `1 <= nums[i] <= n` AND `nums[i] != nums[nums[i]-1]`:
            - This means `nums[i]` is a positive number within the valid range for an index, and it's not in its correct position (`nums[i]` should be at index `nums[i]-1`).
            - Swap `nums[i]` with `nums[nums[i]-1]`.
            - Keep swapping until `nums[i]` is in its correct place, or it's out of range, or it's a duplicate of what's already in its correct place.

3.  **Find the first missing positive:**
    - Iterate `i` from `0` to `n-1`:
        - If `nums[i] != i + 1`, then `i + 1` is the first missing positive. Return `i + 1`.
4.  If all numbers from `1` to `n` are present in their correct positions, then the first missing positive is `n + 1`.

**Tags:** `Array`, `Hash Table`, `Cyclic Sort`, `In-Place Modification`, `Hard`

---
## Problem Description (from LeetCode)

<!-- Placeholder for the full problem description from LeetCode.
     Copy the problem description here from the LeetCode page for easy reference.
     Example: Given an unsorted integer array nums, return the smallest missing positive integer. You must implement an algorithm that runs in O(n) time and uses O(1) auxiliary space.
-->


## Solution Skeleton (Python)

```python
from typing import List

class Solution:
    def firstMissingPositive(self, nums: List[int]) -> int:
        # TODO: Implement solution
        pass

# Example Usage (optional, for testing):
# sol = Solution()
# print(sol.firstMissingPositive([1,2,0]))    # Expected: 3
# print(sol.firstMissingPositive([3,4,-1,1]))  # Expected: 2
# print(sol.firstMissingPositive([7,8,9,11,12]))# Expected: 1
# print(sol.firstMissingPositive([1]))        # Expected: 2
# print(sol.firstMissingPositive([2,1]))      # Expected: 3
```
---
