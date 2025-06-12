# Majority Element (LC 169)

**Link:** [https://leetcode.com/problems/majority-element/](https://leetcode.com/problems/majority-element/)

**Difficulty:** Easy

**Hint/Core Idea:**
Boyer-Moore Voting Algorithm.
The algorithm works on the principle that if there is a majority element (appears more than n/2 times), it will remain the `candidate` after all cancellations.

1.  Initialize `candidate = None` and `count = 0`.
2.  Iterate through the `nums` array:
    -   If `count == 0`, set `candidate = current_num` and `count = 1`.
    -   Else if `current_num == candidate`, increment `count`.
    -   Else (if `current_num != candidate`), decrement `count`.
3.  The `candidate` variable will hold the majority element. (The problem guarantees a majority element always exists).

Other approaches:
-   **Hash Map:** Count frequencies of each element. O(n) time, O(n) space.
-   **Sorting:** Sort the array. The element at index `n/2` will be the majority element. O(n log n) time, O(1) or O(n) space depending on sort.

**Tags:** `Array`, `Hash Table`, `Sorting`, `Counting`, `Divide and Conquer`, `Boyer-Moore Voting Algorithm`

---
## Problem Description (from LeetCode)

<!-- Placeholder for the full problem description from LeetCode.
     Copy the problem description here from the LeetCode page for easy reference.
     Example: Given an array nums of size n, return the majority element. The majority element is the element that appears more than ⌊n / 2⌋ times. You may assume that the majority element always exists in the array.
-->


## Solution Skeleton (Python)

```python
from typing import List

class Solution:
    def majorityElement(self, nums: List[int]) -> int:
        # TODO: Implement solution (e.g., Boyer-Moore)
        pass

# Example Usage (optional, for testing):
# sol = Solution()
# print(sol.majorityElement([3,2,3]))       # Expected: 3
# print(sol.majorityElement([2,2,1,1,1,2,2])) # Expected: 2
# print(sol.majorityElement([1]))           # Expected: 1
```
---
