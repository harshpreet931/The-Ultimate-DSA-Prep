# Non-overlapping Intervals (LC 435)

**Link:** [https://leetcode.com/problems/non-overlapping-intervals/](https://leetcode.com/problems/non-overlapping-intervals/)

**Difficulty:** Medium

**Hint/Core Idea:**
Greedy approach. The goal is to find the minimum number of intervals to remove to make the rest non-overlapping. This is equivalent to finding the maximum number of non-overlapping intervals you can keep.

1.  **Sort by End Times:** Sort the intervals based on their end times. If end times are equal, sorting by start times can also be beneficial but primary sort is by end time.
    *(Alternative: Sort by Start Times. If sorting by start times, when an overlap occurs, you remove the interval that ends later, as this will free up space earlier for more potential intervals).*

2.  **Greedy Selection (if sorted by end times):**
    - Initialize `count_kept = 0` and `last_kept_end_time = -infinity`.
    - Iterate through the sorted intervals:
        - If the current interval's `start_time >= last_kept_end_time`:
            - This interval does not overlap with the last kept interval.
            - Keep this interval: `count_kept++`.
            - Update `last_kept_end_time = current_interval.end_time`.
    - The minimum number of intervals to remove is `total_intervals - count_kept`.

**Tags:** `Array`, `Sorting`, `Greedy`, `Intervals`

---
## Problem Description (from LeetCode)

<!-- Placeholder for the full problem description from LeetCode.
     Copy the problem description here from the LeetCode page for easy reference.
     Example: Given an array of intervals where intervals[i] = [start_i, end_i], return the minimum number of intervals you need to remove to make the rest of the intervals non-overlapping.
-->


## Solution Skeleton (Python)

```python
from typing import List

class Solution:
    def eraseOverlapIntervals(self, intervals: List[List[int]]) -> int:
        # TODO: Implement solution
        pass

# Example Usage (optional, for testing):
# sol = Solution()
# print(sol.eraseOverlapIntervals([[1,2],[2,3],[3,4],[1,3]])) # Expected: 1 (remove [1,3])
# print(sol.eraseOverlapIntervals([[1,2],[1,2],[1,2]]))       # Expected: 2
# print(sol.eraseOverlapIntervals([[1,2],[2,3]]))          # Expected: 0
# print(sol.eraseOverlapIntervals([[1,100],[11,22],[1,11],[2,12]])) # Expected: 2 (e.g. remove [1,100] and [1,11])
```
---
