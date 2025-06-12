# Find the Duplicate Number (LC 287)

**Link:** [https://leetcode.com/problems/find-the-duplicate-number/](https://leetcode.com/problems/find-the-duplicate-number/)

**Difficulty:** Medium

**Hint/Core Idea:**
The problem states there are `n+1` integers in `nums` where each integer is in the range `[1, n]` inclusive, and there is only one repeated number.

**Approach 1: Floyd's Cycle-Finding Algorithm (Tortoise and Hare)**
- This approach views the array as a linked list where `nums[i]` points to the next node. Since there's a duplicate, there must be a cycle.
1.  Initialize `tortoise = nums[0]` and `hare = nums[0]`.
2.  **Find intersection point:**
    -   Move `tortoise` one step: `tortoise = nums[tortoise]`.
    -   Move `hare` two steps: `hare = nums[nums[hare]]`.
    -   Repeat until `tortoise == hare`.
3.  **Find cycle entrance:**
    -   Reset `tortoise` to `nums[0]`.
    -   Move both `tortoise` and `hare` one step at a time: `tortoise = nums[tortoise]`, `hare = nums[hare]`.
    -   The point where they meet again is the start of the cycle, which is the duplicate number. Return `tortoise` (or `hare`).

**Approach 2: Binary Search on the Range of Numbers**
- The numbers are in the range `[1, n]`. We can binary search for the duplicate number in this range.
- For a `mid` value in the range `[1, n]`:
    - Count how many numbers in `nums` are less than or equal to `mid`. Let this be `count`.
    - If `count > mid`, it means the duplicate number is in the range `[1, mid]`. So, `high = mid`.
    - Else (`count <= mid`), the duplicate number is in the range `[mid+1, n]`. So, `low = mid + 1`.
- The loop continues until `low == high`, which will be the duplicate number.

**Tags:** `Array`, `Two Pointers`, `Binary Search`, `Cycle Detection`, `Bit Manipulation` (less common for this specific problem variant)

---
## Problem Description (from LeetCode)

<!-- Placeholder for the full problem description from LeetCode.
     Copy the problem description here from the LeetCode page for easy reference.
     Example: Given an array of integers nums containing n + 1 integers where each integer is in the range [1, n] inclusive. There is only one repeated number in nums, return this repeated number. You must solve the problem without modifying the array nums and uses only constant extra space.
-->


## Solution Skeleton (Python)

```python
from typing import List

class Solution:
    def findDuplicate(self, nums: List[int]) -> int:
        # TODO: Implement solution (e.g., Floyd's cycle detection)
        pass

# Example Usage (optional, for testing):
# sol = Solution()
# print(sol.findDuplicate([1,3,4,2,2]))    # Expected: 2
# print(sol.findDuplicate([3,1,3,4,2]))    # Expected: 3
# print(sol.findDuplicate([1,1]))          # Expected: 1
# print(sol.findDuplicate([1,1,2]))        # Expected: 1
# print(sol.findDuplicate([2,2,2,2,2]))    # Expected: 2
```
---
