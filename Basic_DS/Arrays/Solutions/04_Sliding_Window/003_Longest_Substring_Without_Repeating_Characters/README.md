# Longest Substring Without Repeating Characters (LC 3)

**Link:** [https://leetcode.com/problems/longest-substring-without-repeating-characters/](https://leetcode.com/problems/longest-substring-without-repeating-characters/)

**Tags:** `Sliding Window`, `HashMap`, `Two Pointers`


## Problem Description (from LeetCode)

Given a string s, find the length of the longest substring without duplicate characters. Super simple!

Example 1:
Input: s = "abcabcbb"
Output: 3
Explanation: The answer is "abc", with the length of 3.

Example 2:
Input: s = "bbbbb"
Output: 1
Explanation: The answer is "b", with the length of 1.

Example 3:
Input: s = "pwwkew"
Output: 3
Explanation: The answer is "wke", with the length of 3.
Notice that the answer must be a substring, "pwke" is a subsequence and not a substring.

---
## **Hint/Core Idea:**
<details>
<summary>Click to expand hint</summary>

Use a sliding window approach, a fancy word for a simple two-pointer technique. What we do is maintain a window of characters that do not repeat. If we encounter a character that is already in the window, we shrink the window from the left until there are no duplicates. This way, we can efficiently find the longest substring without repeating characters.
</details>

<br>


## Solution (Java)

```java
class Solution {
    public int lengthOfLongestSubstring(String s) {
        HashMap<Character, Integer> mp = new HashMap<>();
        int maxLen = 0;

        for (int left = 0, right = 0; right < s.length(); right++)
        {
            char c = s.charAt(right);

            while (mp.containsKey(c))
            {
                char toDel = s.charAt(left++);
                mp.put(toDel, mp.getOrDefault(toDel, 0) - 1);
                if (mp.get(toDel) == 0) mp.remove(toDel); 
            }

            mp.put(c, mp.getOrDefault(c, 0) + 1);
            maxLen = Math.max(maxLen, right - left + 1);
        }

        return maxLen;
    }
}