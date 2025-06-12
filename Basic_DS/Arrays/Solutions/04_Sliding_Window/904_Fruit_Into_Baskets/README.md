# Fruit Into Baskets (LC 904)

**Link:** [https://leetcode.com/problems/fruit-into-baskets/](https://leetcode.com/problems/fruit-into-baskets/)

**Difficulty:** Medium

**Hint/Core Idea:**
This problem is equivalent to finding the "Longest Subarray with At Most 2 Distinct Elements".
Use a sliding window approach:
- `window_start = 0`, `max_length = 0`.
- `fruit_frequency = {}` (to store counts of fruit types in the current window).
- Expand window (increment `window_end`):
    - Add `fruits[window_end]` to `fruit_frequency`.
- While `len(fruit_frequency) > 2` (window is invalid, more than 2 types of fruit):
    - `left_fruit = fruits[window_start]`
    - Decrement `fruit_frequency[left_fruit]`.
    - If `fruit_frequency[left_fruit] == 0`, remove `left_fruit` from `fruit_frequency`.
    - Increment `window_start` (shrink window from left).
- Update `max_length = max(max_length, window_end - window_start + 1)`.

**Tags:** `Array`, `Sliding Window`, `Hash Table`, `Frequency Counter`

---
## Problem Description (from LeetCode)

<!-- Placeholder for the full problem description from LeetCode.
     Copy the problem description here from the LeetCode page for easy reference.
     Example: You are visiting a farm that has a single row of fruit trees arranged from left to right. The trees are represented by an integer array fruits where fruits[i] is the type of fruit the ith tree produces. You want to collect as much fruit as possible. However, the owner has some strict rules that you must follow: You only have two baskets, and each basket can only hold a single type of fruit. There is no limit on the amount of fruit each basket can hold. Starting from any tree of your choice, you must pick exactly one fruit from every tree (including the start tree) while moving to the right. The picked fruits must fit in one of your baskets. Once you reach a tree with fruit that cannot fit in your baskets, you must stop. Given the integer array fruits, return the maximum number of fruits you can pick.
-->


## Solution Skeleton (Python)

```python
from typing import List
from collections import Counter

class Solution:
    def totalFruit(self, fruits: List[int]) -> int:
        # TODO: Implement solution
        pass

# Example Usage (optional, for testing):
# sol = Solution()
# print(sol.totalFruit([1,2,1]))       # Expected: 3
# print(sol.totalFruit([0,1,2,2]))     # Expected: 3
# print(sol.totalFruit([1,2,3,2,2]))   # Expected: 4
# print(sol.totalFruit([3,3,3,1,2,1,1,2,3,3,4])) # Expected: 5
```
---
