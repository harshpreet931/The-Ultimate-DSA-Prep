# Merge Sorted Array (LC 88)

**Link:** [https://leetcode.com/problems/merge-sorted-array/](https://leetcode.com/problems/merge-sorted-array/)

**Difficulty:** Easy

**Hint/Core Idea:**
Merging in-place, often requires iterating backwards.

**Tags:** `Array`, `Two Pointers`, `Sorting`

---
## Problem Description (from LeetCode)

<!-- Placeholder for the full problem description from LeetCode.
     Copy the problem description here from the LeetCode page for easy reference.
     Example: You are given two integer arrays nums1 and nums2, sorted in non-decreasing order, and two integers m and n, representing the number of elements in nums1 and nums2 respectively. Merge nums1 and nums2 into a single array sorted in non-decreasing order. The final sorted array should not be returned by the function, but instead be stored inside the array nums1. To accommodate this, nums1 has a length of m + n, where the first m elements denote the elements that should be merged, and the last n elements are set to 0 and should be ignored. nums2 has a length of n.
-->


## Solution Skeleton (Python)

```python
from typing import List

class Solution:
    def merge(self, nums1: List[int], m: int, nums2: List[int], n: int) -> None:
        """
        Do not return anything, modify nums1 in-place instead.
        """
        # TODO: Implement solution
        pass

# Example Usage (optional, for testing):
# sol = Solution()
# nums1_ex1 = [1,2,3,0,0,0]
# m_ex1 = 3
# nums2_ex1 = [2,5,6]
# n_ex1 = 3
# sol.merge(nums1_ex1, m_ex1, nums2_ex1, n_ex1)
# print(nums1_ex1) # Expected: [1,2,2,3,5,6]

# nums1_ex2 = [1]
# m_ex2 = 1
# nums2_ex2 = []
# n_ex2 = 0
# sol.merge(nums1_ex2, m_ex2, nums2_ex2, n_ex2)
# print(nums1_ex2) # Expected: [1]

# nums1_ex3 = [0]
# m_ex3 = 0
# nums2_ex3 = [1]
# n_ex3 = 1
# sol.merge(nums1_ex3, m_ex3, nums2_ex3, n_ex3)
# print(nums1_ex3) # Expected: [1]
```
---
