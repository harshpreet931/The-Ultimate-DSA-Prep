# Find All Anagrams in a String (LC 438)

**Link:** [https://leetcode.com/problems/find-all-anagrams-in-a-string/](https://leetcode.com/problems/find-all-anagrams-in-a-string/)

**Difficulty:** Medium

**Hint/Core Idea:**
Fixed-size sliding window (size of `p`).
1. Create frequency maps for string `p` (`p_freq`) and for the first window in `s` (`s_window_freq`).
2. Compare `p_freq` and `s_window_freq`. If they match, add the starting index of the window to results.
3. Slide the window through `s`:
    - Decrement frequency of the character leaving the window.
    - Increment frequency of the character entering the window.
    - Compare `p_freq` and `s_window_freq` again. If they match, add the new starting index.

**Tags:** `String`, `Sliding Window`, `Hash Table`, `Frequency Counter`

---
## Problem Description (from LeetCode)

<!-- Placeholder for the full problem description from LeetCode.
     Copy the problem description here from the LeetCode page for easy reference.
     Example: Given two strings s and p, return an array of all the start indices of p's anagrams in s. You may return the answer in any order.
-->


## Solution Skeleton (Python)

```python
from typing import List
from collections import Counter

class Solution:
    def findAnagrams(self, s: str, p: str) -> List[int]:
        # TODO: Implement solution
        pass

# Example Usage (optional, for testing):
# sol = Solution()
# print(sol.findAnagrams("cbaebabacd", "abc")) # Expected: [0,6]
# print(sol.findAnagrams("abab", "ab"))       # Expected: [0,1,2]
# print(sol.findAnagrams("af", "be"))         # Expected: []
```
---
