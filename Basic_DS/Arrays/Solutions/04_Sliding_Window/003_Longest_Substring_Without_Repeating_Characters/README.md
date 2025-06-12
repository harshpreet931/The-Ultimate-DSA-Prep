# Longest Substring Without Repeating Characters (LC 3)

**Link:** [https://leetcode.com/problems/longest-substring-without-repeating-characters/](https://leetcode.com/problems/longest-substring-without-repeating-characters/)

**Difficulty:** Medium

**Hint/Core Idea:**
Variable-size sliding window using a hash map (or set) to track characters currently in the window and their last seen positions (if using map for optimization).
- Initialize `max_length = 0`, `window_start = 0`, `char_index_map = {}` (or `char_set = set()`).
- Iterate with `window_end` through the string:
    - `right_char = s[window_end]`
    - If `right_char` is already in `char_index_map` (or `char_set`) and its last seen index `char_index_map[right_char]` is within the current window (`>= window_start`):
        - Shrink the window from the left: `window_start = char_index_map[right_char] + 1`.
    - Update the last seen index of `right_char`: `char_index_map[right_char] = window_end`.
    - Update `max_length = max(max_length, window_end - window_start + 1)`.

**Tags:** `String`, `Sliding Window`, `Hash Table`, `Set`

---
## Problem Description (from LeetCode)

<!-- Placeholder for the full problem description from LeetCode.
     Copy the problem description here from the LeetCode page for easy reference.
     Example: Given a string s, find the length of the longest substring without repeating characters.
-->


## Solution Skeleton (Python)

```python
class Solution:
    def lengthOfLongestSubstring(self, s: str) -> int:
        # TODO: Implement solution
        pass

# Example Usage (optional, for testing):
# sol = Solution()
# print(sol.lengthOfLongestSubstring("abcabcbb")) # Expected: 3 (abc)
# print(sol.lengthOfLongestSubstring("bbbbb"))    # Expected: 1 (b)
# print(sol.lengthOfLongestSubstring("pwwkew"))   # Expected: 3 (wke or kew)
# print(sol.lengthOfLongestSubstring(""))        # Expected: 0
# print(sol.lengthOfLongestSubstring(" "))        # Expected: 1
# print(sol.lengthOfLongestSubstring("dvdf"))     # Expected: 3 (vdf)
```
---
