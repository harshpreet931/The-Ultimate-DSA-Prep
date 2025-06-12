# Merge Intervals (LC 56)

**Link:** [https://leetcode.com/problems/merge-intervals/](https://leetcode.com/problems/merge-intervals/)

**Difficulty:** Medium

**Hint/Core Idea:**
1. Sort the intervals based on their start times.
2. Initialize an empty list `merged_intervals`.
3. Iterate through the sorted intervals:
   - If `merged_intervals` is empty or the current interval does not overlap with the last interval in `merged_intervals` (i.e., `current_interval.start > merged_intervals[-1].end`), then add the current interval to `merged_intervals`.
   - Else (if there is an overlap), merge the current interval with the last interval in `merged_intervals` by updating the end time of the last interval: `merged_intervals[-1].end = max(merged_intervals[-1].end, current_interval.end)`.

**Tags:** `Array`, `Sorting`, `Intervals`

---
## Problem Description (from LeetCode)

<!-- Placeholder for the full problem description from LeetCode.
     Copy the problem description here from the LeetCode page for easy reference.
     Example: Given an array of intervals where intervals[i] = [start_i, end_i], merge all overlapping intervals, and return an array of the non-overlapping intervals that cover all the intervals in the input.
-->


## Solution Skeleton (Python)

```python
from typing import List

class Solution:
    def merge(self, intervals: List[List[int]]) -> List[List[int]]:
        # TODO: Implement solution
        pass

# Example Usage (optional, for testing):
# sol = Solution()
# print(sol.merge([[1,3],[2,6],[8,10],[15,18]])) # Expected: [[1,6],[8,10],[15,18]]
# print(sol.merge([[1,4],[4,5]]))                # Expected: [[1,5]]
# print(sol.merge([[1,4],[0,4]]))                # Expected: [[0,4]]
# print(sol.merge([[1,4],[0,0]]))                # Expected: [[0,0],[1,4]] (after sorting) or [[0,0],[1,4]]
```
---
