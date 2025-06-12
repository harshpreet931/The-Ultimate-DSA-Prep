# Remove Element (LC 27)

**Link:** [https://leetcode.com/problems/remove-element/](https://leetcode.com/problems/remove-element/)

**Difficulty:** Easy

**Hint/Core Idea:**
Similar to Remove Duplicates, in-place removal.

**Tags:** `Array`, `Two Pointers`

---
## Problem Description (from LeetCode)

<!-- Placeholder for the full problem description from LeetCode.
     Copy the problem description here from the LeetCode page for easy reference.
     Example: Given an integer array nums and an integer val, remove all occurrences of val in nums in-place. The order of the elements may be changed. Then return the number of elements in nums which are not equal to val.
-->


## Solution Skeleton (Python)

```python
from typing import List

class Solution:
    def removeElement(self, nums: List[int], val: int) -> int:
        # TODO: Implement solution
        pass

# Example Usage (optional, for testing):
# sol = Solution()
# nums1_ex1 = [3,2,2,3]
# val_ex1 = 3
# k_ex1 = sol.removeElement(nums1_ex1, val_ex1)
# print(f"k = {k_ex1}, nums = {sorted(nums1_ex1[:k_ex1])}") # Expected: k = 2, nums = [2,2] (order doesn't matter for remaining)

# nums1_ex2 = [0,1,2,2,3,0,4,2]
# val_ex2 = 2
# k_ex2 = sol.removeElement(nums1_ex2, val_ex2)
# print(f"k = {k_ex2}, nums = {sorted(nums1_ex2[:k_ex2])}") # Expected: k = 5, nums = [0,0,1,3,4] (order doesn't matter for remaining)
```
---
