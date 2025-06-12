# Longest Repeating Character Replacement (LC 424)

**Link:** [https://leetcode.com/problems/longest-repeating-character-replacement/](https://leetcode.com/problems/longest-repeating-character-replacement/)

**Difficulty:** Medium

**Hint/Core Idea:**
Sliding window approach.
- Maintain a frequency map (`char_freq`) of characters within the current window.
- Keep track of the frequency of the most frequent character in the current window (`max_freq_in_window`).
- `window_start = 0`, `max_length = 0`.
- Expand window (increment `window_end`):
    - Add `s[window_end]` to `char_freq`.
    - Update `max_freq_in_window = max(max_freq_in_window, char_freq[s[window_end]])`.
- Check window validity: `window_length = window_end - window_start + 1`.
- If `(window_length - max_freq_in_window) > k`:
    - The window is invalid (too many characters to replace). Shrink it from the left.
    - Decrement `char_freq[s[window_start]]`.
    - Increment `window_start`.
    - (Note: `max_freq_in_window` doesn't need to be recomputed precisely when shrinking; it's okay if it's an overestimate. The window will expand again and `max_freq_in_window` will be correctly updated if a new character becomes most frequent or the current most frequent character's count increases.)
- Update `max_length = max(max_length, window_length)`.

**Tags:** `String`, `Sliding Window`, `Hash Table`, `Frequency Counter`

---
## Problem Description (from LeetCode)

<!-- Placeholder for the full problem description from LeetCode.
     Copy the problem description here from the LeetCode page for easy reference.
     Example: You are given a string s and an integer k. You can choose any character of the string and change it to any other uppercase English character. You can perform this operation at most k times. Return the length of the longest substring containing the same letter you can get after performing the above operations.
-->


## Solution Skeleton (Python)

```python
from collections import Counter

class Solution:
    def characterReplacement(self, s: str, k: int) -> int:
        # TODO: Implement solution
        pass

# Example Usage (optional, for testing):
# sol = Solution()
# print(sol.characterReplacement("ABAB", 2))    # Expected: 4
# print(sol.characterReplacement("AABABBA", 1)) # Expected: 4
# print(sol.characterReplacement("ABCDE", 1))   # Expected: 2
```
---
