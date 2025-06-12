# Insert Interval (LC 57)

**Link:** [https://leetcode.com/problems/insert-interval/](https://leetcode.com/problems/insert-interval/)

**Difficulty:** Medium

**Hint/Core Idea:**
Iterate through the sorted list of non-overlapping intervals and build a new list of merged intervals.
There are three main cases for each existing interval `current_interval` in relation to `newInterval`:
1.  `current_interval.end < newInterval.start`: `current_interval` is completely before `newInterval` and does not overlap. Add `current_interval` to the result.
2.  `current_interval.start > newInterval.end`: `current_interval` is completely after `newInterval` and does not overlap. Add `newInterval` (if not already added) to the result, then add `current_interval`. Mark `newInterval` as added.
3.  Overlap: `current_interval` overlaps with `newInterval`. Merge them by updating `newInterval`:
    `newInterval.start = min(newInterval.start, current_interval.start)`
    `newInterval.end = max(newInterval.end, current_interval.end)`
    Do not add anything to the result yet; continue merging `newInterval` with subsequent overlapping intervals.

After iterating through all `intervals`:
- If `newInterval` has not been added yet (e.g., it overlaps with the last interval or should be placed at the end), add the (potentially modified) `newInterval` to the result.

**Tags:** `Array`, `Intervals`

---
## Problem Description (from LeetCode)

<!-- Placeholder for the full problem description from LeetCode.
     Copy the problem description here from the LeetCode page for easy reference.
     Example: You are given an array of non-overlapping intervals where intervals[i] = [start_i, end_i] represent the start and the end of the ith interval and intervals is sorted in ascending order by start_i. You are also given an interval newInterval = [start, end] that represents the start and end of another interval. Insert newInterval into intervals such that intervals is still sorted in ascending order by start_i and intervals still does not have any overlapping intervals (merge overlapping intervals if necessary). Return intervals after the insertion.
-->


## Solution Skeleton (Python)

```python
from typing import List

class Solution:
    def insert(self, intervals: List[List[int]], newInterval: List[int]) -> List[List[int]]:
        # TODO: Implement solution
        pass

# Example Usage (optional, for testing):
# sol = Solution()
# print(sol.insert([[1,3],[6,9]], [2,5]))          # Expected: [[1,5],[6,9]]
# print(sol.insert([[1,2],[3,5],[6,7],[8,10],[12,16]], [4,8])) # Expected: [[1,2],[3,10],[12,16]]
# print(sol.insert([], [5,7]))                       # Expected: [[5,7]]
# print(sol.insert([[1,5]], [2,3]))                  # Expected: [[1,5]]
# print(sol.insert([[1,5]], [0,0]))                  # Expected: [[0,0],[1,5]]
# print(sol.insert([[1,5]], [6,8]))                  # Expected: [[1,5],[6,8]]
```
---
