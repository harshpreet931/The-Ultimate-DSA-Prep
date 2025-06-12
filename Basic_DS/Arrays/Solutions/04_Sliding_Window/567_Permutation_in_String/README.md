# Permutation in String (LC 567)

**Link:** [https://leetcode.com/problems/permutation-in-string/](https://leetcode.com/problems/permutation-in-string/)

**Difficulty:** Medium

**Hint/Core Idea:**
Very similar to "Find All Anagrams in a String" (LC 438). Use a fixed-size sliding window (size of `s1`).
1. Create frequency maps for string `s1` (`s1_freq`) and for the first window in `s2` (`s2_window_freq`).
2. If `s1_freq` and `s2_window_freq` match, a permutation exists, return `True`.
3. Slide the window through `s2`:
    - Decrement frequency of the character leaving the window from `s2_window_freq`.
    - Increment frequency of the character entering the window into `s2_window_freq`.
    - If `s1_freq` and `s2_window_freq` match, return `True`.
4. If the loop finishes without a match, return `False`.

**Tags:** `String`, `Sliding Window`, `Hash Table`, `Frequency Counter`

---
## Problem Description (from LeetCode)

<!-- Placeholder for the full problem description from LeetCode.
     Copy the problem description here from the LeetCode page for easy reference.
     Example: Given two strings s1 and s2, return true if s2 contains a permutation of s1, or false otherwise. In other words, return true if one of s1's permutations is the substring of s2.
-->


## Solution Skeleton (Python)

```python
from typing import List
from collections import Counter

class Solution:
    def checkInclusion(self, s1: str, s2: str) -> bool:
        # TODO: Implement solution
        pass

# Example Usage (optional, for testing):
# sol = Solution()
# print(sol.checkInclusion("ab", "eidbaooo"))  # Expected: True (ba is a permutation of ab)
# print(sol.checkInclusion("ab", "eidboaoo"))  # Expected: False
# print(sol.checkInclusion("a", "b"))          # Expected: False
# print(sol.checkInclusion("adc", "dcda"))     # Expected: True (cda is a permutation of adc)
```
---
