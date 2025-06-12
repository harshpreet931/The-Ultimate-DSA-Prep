# Pair with given sum in a sorted (and possibly rotated) array (GFG)

**Link (GeeksforGeeks):** [https://www.geeksforgeeks.org/given-a-sorted-and-rotated-array-find-if-there-is-a-pair-with-a-given-sum/](https://www.geeksforgeeks.org/given-a-sorted-and-rotated-array-find-if-there-is-a-pair-with-a-given-sum/)

**Similar to:** LC 167. Two Sum II - Input Array Is Sorted ([https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/](https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/))

**Difficulty:** Easy (GFG)

**Hint/Core Idea:**
- If the array is sorted (not rotated): Use the classic two-pointer approach (start and end). This is identical to LC 167.
- If the array is sorted AND rotated:
    1. Find the pivot point (the index of the smallest element, where rotation occurs). This can be done in O(log n) using a modified binary search.
    2. Once the pivot is found, the array can be conceptually viewed as two sorted subarrays or treated as a single sorted circular array.
    3. Apply the two-pointer technique. Initialize `left` to the pivot and `right` to `(pivot - 1 + n) % n`.
    4. Move `left` and `right` pointers towards each other (circularly) based on whether the current sum is less than, greater than, or equal to the target sum.

**Tags:** `Array`, `Two Pointers`, `Binary Search`, `Searching`, `Sorting`

---
## Problem Description (from GeeksforGeeks)

<!-- Placeholder for the full problem description from GFG.
     Copy the problem description here from the GFG page for easy reference.
     Example: Given an array that is sorted and then rotated around an unknown point, find if the array has a pair with a given sum ‘x’.
-->


## Solution Skeleton (Python)

```python
from typing import List

# For a simple sorted array (like LC 167)
class SolutionLC167:
    def findPair(self, nums: List[int], target: int) -> bool: # Or return indices
        # TODO: Implement two-pointer for sorted array
        left, right = 0, len(nums) - 1
        while left < right:
            current_sum = nums[left] + nums[right]
            if current_sum == target:
                return True # Or return [left+1, right+1] for 1-based indexing
            elif current_sum < target:
                left += 1
            else:
                right -= 1
        return False

# For a sorted and rotated array (GFG variation)
class SolutionGFG:
    def findPairInSortedRotated(self, nums: List[int], target: int) -> bool:
        n = len(nums)
        if n < 2:
            return False

        # 1. Find pivot (index of the smallest element)
        pivot = -1
        # Simple linear scan for pivot (O(n)), can be optimized to O(log n)
        for i in range(n - 1):
            if nums[i] > nums[i+1]:
                pivot = i + 1
                break
        if pivot == -1: # Array is not rotated or all elements are same
            pivot = 0


        # 2. Apply two pointers on the conceptual sorted array
        # left starts at the smallest element, right starts at the largest element
        left = pivot
        right = (pivot - 1 + n) % n

        while left != right: # Pointers will cross if pair not found
            current_sum = nums[left] + nums[right]
            if current_sum == target:
                return True
            elif current_sum < target:
                left = (left + 1) % n
            else:
                right = (right - 1 + n) % n
        return False


# Example Usage (optional, for testing):
# sol_lc = SolutionLC167()
# print(f"LC 167 like: {sol_lc.findPair([2,7,11,15], 9)}") # Expected: True

# sol_gfg = SolutionGFG()
# print(f"GFG Rotated: {sol_gfg.findPairInSortedRotated([11, 15, 6, 8, 9, 10], 16)}") # Expected: True
# print(f"GFG Rotated: {sol_gfg.findPairInSortedRotated([11, 15, 26, 38, 2, 10], 35)}") # Expected: False
# print(f"GFG Rotated: {sol_gfg.findPairInSortedRotated([1,2,3,4,5], 9)}") # Expected: True (pivot=0)
```
---
