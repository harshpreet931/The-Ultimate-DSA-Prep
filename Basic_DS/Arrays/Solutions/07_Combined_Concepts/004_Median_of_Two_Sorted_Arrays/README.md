# Median of Two Sorted Arrays (LC 4)

**Link:** [https://leetcode.com/problems/median-of-two-sorted-arrays/](https://leetcode.com/problems/median-of-two-sorted-arrays/)

**Difficulty:** Hard

**Hint/Core Idea:**
This is a classic hard problem that requires a binary search approach on the partitions of the two arrays. The goal is to find a partition `(partitionX, partitionY)` such that all elements on the left side of the partitions are less than or equal to all elements on the right side, and the total number of elements on the left is `(m+n+1)/2`.

1.  Ensure `nums1` is the smaller array to simplify partitioning ranges. If not, swap `nums1` and `nums2`. Let `m = len(nums1)` and `n = len(nums2)`.
2.  Binary search for `partitionX` in `nums1` (from `0` to `m`).
    -   `partitionY = (m + n + 1) // 2 - partitionX`. This ensures that the total number of elements in the left halves is correct for finding the median.
3.  Determine the four key elements around the partitions:
    -   `maxLeftX = nums1[partitionX - 1]` if `partitionX > 0`, else `-infinity`.
    -   `minRightX = nums1[partitionX]` if `partitionX < m`, else `+infinity`.
    -   `maxLeftY = nums2[partitionY - 1]` if `partitionY > 0`, else `-infinity`.
    -   `minRightY = nums2[partitionY]` if `partitionY < n`, else `+infinity`.
4.  Check if the correct partition is found:
    -   `maxLeftX <= minRightY` AND `maxLeftY <= minRightX`.
    -   If true:
        -   If `(m + n)` is odd, the median is `max(maxLeftX, maxLeftY)`.
        -   If `(m + n)` is even, the median is `(max(maxLeftX, maxLeftY) + min(minRightX, minRightY)) / 2.0`.
    -   If `maxLeftX > minRightY`: The partition in `nums1` is too far to the right. Move `partitionX` left (`high = partitionX - 1`).
    -   Else (`maxLeftY > minRightX`): The partition in `nums1` is too far to the left. Move `partitionX` right (`low = partitionX + 1`).

**Tags:** `Array`, `Binary Search`, `Divide and Conquer`, `Hard`

---
## Problem Description (from LeetCode)

<!-- Placeholder for the full problem description from LeetCode.
     Copy the problem description here from the LeetCode page for easy reference.
     Example: Given two sorted arrays nums1 and nums2 of size m and n respectively, return the median of the two sorted arrays. The overall run time complexity should be O(log (m+n)).
-->


## Solution Skeleton (Python)

```python
from typing import List
import math

class Solution:
    def findMedianSortedArrays(self, nums1: List[int], nums2: List[int]) -> float:
        # TODO: Implement solution
        pass

# Example Usage (optional, for testing):
# sol = Solution()
# print(sol.findMedianSortedArrays([1,3], [2]))       # Expected: 2.0
# print(sol.findMedianSortedArrays([1,2], [3,4]))     # Expected: 2.5
# print(sol.findMedianSortedArrays([0,0], [0,0]))     # Expected: 0.0
# print(sol.findMedianSortedArrays([], [1]))          # Expected: 1.0
# print(sol.findMedianSortedArrays([2], []))          # Expected: 2.0
```
---
