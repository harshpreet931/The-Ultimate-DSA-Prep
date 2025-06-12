# Remove Duplicates from Sorted Array (LC 26)

**Link:** [https://leetcode.com/problems/remove-duplicates-from-sorted-array/](https://leetcode.com/problems/remove-duplicates-from-sorted-array/)

**Difficulty:** Easy

**Hint/Core Idea:**
In-place modification using two pointers (slow and fast).

**Tags:** `Array`, `Two Pointers`

---
## Problem Description (from LeetCode)

<!-- Placeholder for the full problem description from LeetCode.
     Copy the problem description here from the LeetCode page for easy reference.
     Example: Given an integer array nums sorted in non-decreasing order, remove the duplicates in-place such that each unique element appears only once. The relative order of the elements should be kept the same. Then return the number of unique elements in nums.
-->


## Solution Skeleton (Python)

```python
from typing import List

class Solution:
    def removeDuplicates(self, nums: List[int]) -> int:
        # TODO: Implement solution
        pass

# Example Usage (optional, for testing):
# sol = Solution()
# nums1_ex1 = [1,1,2]
# k_ex1 = sol.removeDuplicates(nums1_ex1)
# print(f"k = {k_ex1}, nums = {nums1_ex1[:k_ex1]}") # Expected: k = 2, nums = [1,2]

# nums1_ex2 = [0,0,1,1,1,2,2,3,3,4]
# k_ex2 = sol.removeDuplicates(nums1_ex2)
# print(f"k = {k_ex2}, nums = {nums1_ex2[:k_ex2]}") # Expected: k = 5, nums = [0,1,2,3,4]
```
---
