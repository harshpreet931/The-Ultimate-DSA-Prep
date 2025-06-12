# Minimum Window Substring (LC 76)

**Link:** [https://leetcode.com/problems/minimum-window-substring/](https://leetcode.com/problems/minimum-window-substring/)

**Difficulty:** Hard

**Hint/Core Idea:**
Classic hard sliding window problem.
1. Create a frequency map (`t_freq`) for characters in string `t`.
2. Initialize `window_freq` for characters in the current window in `s`.
3. `required_chars`: number of unique characters in `t`.
4. `formed_chars`: number of unique characters in `t` that are currently satisfied by the window.
5. `window_start = 0`, `min_len = float('inf')`, `result_substring = ""`.
6. Expand window (increment `window_end`):
   - Add `s[window_end]` to `window_freq`.
   - If `s[window_end]` is in `t_freq` and `window_freq[s[window_end]] == t_freq[s[window_end]]`, increment `formed_chars`.
7. Contract window (while `formed_chars == required_chars`):
   - If current window length is less than `min_len`, update `min_len` and `result_substring`.
   - Remove `s[window_start]` from `window_freq`.
   - If `s[window_start]` is in `t_freq` and `window_freq[s[window_start]] < t_freq[s[window_start]]`, decrement `formed_chars`.
   - Increment `window_start`.

**Tags:** `String`, `Sliding Window`, `Hash Table`, `Frequency Counter`

---
## Problem Description (from LeetCode)

<!-- Placeholder for the full problem description from LeetCode.
     Copy the problem description here from the LeetCode page for easy reference.
     Example: Given two strings s and t of lengths m and n respectively, return the minimum window substring of s such that every character in t (including duplicates) is included in the window. If there is no such substring, return the empty string "".
-->


## Solution Skeleton (Python)

```python
from typing import List
from collections import Counter

class Solution:
    def minWindow(self, s: str, t: str) -> str:
        # TODO: Implement solution
        pass

# Example Usage (optional, for testing):
# sol = Solution()
# print(sol.minWindow("ADOBECODEBANC", "ABC")) # Expected: "BANC"
# print(sol.minWindow("a", "a"))             # Expected: "a"
# print(sol.minWindow("a", "aa"))            # Expected: ""
# print(sol.minWindow("aa", "aa"))           # Expected: "aa"
```
---
