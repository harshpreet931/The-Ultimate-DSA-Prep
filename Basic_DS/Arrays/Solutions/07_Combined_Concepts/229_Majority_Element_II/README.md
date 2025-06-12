# Majority Element II (LC 229)

**Link:** [https://leetcode.com/problems/majority-element-ii/](https://leetcode.com/problems/majority-element-ii/)

**Difficulty:** Medium

**Hint/Core Idea:**
Extended Boyer-Moore Voting Algorithm. Since we are looking for elements appearing more than `n/3` times, there can be at most two such elements.

1.  Initialize two candidates (`candidate1`, `candidate2`) and their counts (`count1`, `count2`) to `None` and `0` respectively.
2.  **First Pass (Finding Candidates):** Iterate through `nums`:
    -   If `num == candidate1`, increment `count1`.
    -   Else if `num == candidate2`, increment `count2`.
    -   Else if `count1 == 0`, set `candidate1 = num`, `count1 = 1`.
    -   Else if `count2 == 0`, set `candidate2 = num`, `count2 = 1`.
    -   Else (if `num` is different from both candidates and counts are non-zero), decrement both `count1` and `count2`.
3.  **Second Pass (Verifying Candidates):**
    -   Reset `count1 = 0`, `count2 = 0`.
    -   Iterate through `nums` again to count the actual occurrences of `candidate1` and `candidate2`.
4.  Construct the result list:
    -   If `count1 > len(nums) // 3`, add `candidate1` to results.
    -   If `count2 > len(nums) // 3` AND `candidate1 != candidate2` (to avoid adding same element twice if it was picked for both candidate slots initially), add `candidate2` to results.
    -   Return the results.

**Tags:** `Array`, `Hash Table`, `Sorting`, `Counting`, `Boyer-Moore Voting Algorithm`

---
## Problem Description (from LeetCode)

<!-- Placeholder for the full problem description from LeetCode.
     Copy the problem description here from the LeetCode page for easy reference.
     Example: Given an integer array of size n, find all elements that appear more than ⌊ n/3 ⌋ times.
-->


## Solution Skeleton (Python)

```python
from typing import List

class Solution:
    def majorityElement(self, nums: List[int]) -> List[int]:
        # TODO: Implement solution
        pass

# Example Usage (optional, for testing):
# sol = Solution()
# print(sol.majorityElement([3,2,3]))       # Expected: [3]
# print(sol.majorityElement([1]))           # Expected: [1]
# print(sol.majorityElement([1,2]))         # Expected: [1,2]
# print(sol.majorityElement([2,2]))         # Expected: [2]
# print(sol.majorityElement([1,1,1,3,3,2,2,2])) # Expected: [1,2]
```
---
