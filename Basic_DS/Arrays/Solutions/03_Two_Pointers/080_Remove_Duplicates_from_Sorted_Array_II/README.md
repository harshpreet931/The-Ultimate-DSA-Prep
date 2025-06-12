# Remove Duplicates from Sorted Array II (LC 80)

**Link:** [https://leetcode.com/problems/remove-duplicates-from-sorted-array-ii/](https://leetcode.com/problems/remove-duplicates-from-sorted-array-ii/)

**Difficulty:** Medium

**Hint/Core Idea:**
Variation of "Remove Duplicates from Sorted Array", allowing at most two occurrences of each element.
Use two pointers: `i` (slow pointer for where to place the next valid element) and `j` (fast pointer iterating through the array).
An element `nums[j]` can be placed at `nums[i]` if `i < 2` (always allow first two elements) OR `nums[j] > nums[i-2]` (current element is different from the element two positions before the insert position, ensuring no more than two duplicates).

**Tags:** `Array`, `Two Pointers`

---
## Problem Description (from LeetCode)

<!-- Placeholder for the full problem description from LeetCode.
     Copy the problem description here from the LeetCode page for easy reference.
     Example: Given an integer array nums sorted in non-decreasing order, remove some duplicates in-place such that each unique element appears at most twice. The relative order of the elements should be kept the same. Then return the number of elements after removing the duplicates.
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
# nums1_ex1 = [1,1,1,2,2,3]
# k_ex1 = sol.removeDuplicates(nums1_ex1)
# print(f"k = {k_ex1}, nums = {nums1_ex1[:k_ex1]}") # Expected: k = 5, nums = [1,1,2,2,3]

# nums1_ex2 = [0,0,1,1,1,1,2,3,3]
# k_ex2 = sol.removeDuplicates(nums1_ex2)
# print(f"k = {k_ex2}, nums = {nums1_ex2[:k_ex2]}") # Expected: k = 7, nums = [0,0,1,1,2,3,3]
```
---
