# Max Sum Subarray of size K (GFG)

**Link (GeeksforGeeks):** [https://www.geeksforgeeks.org/find-maximum-minimum-sum-subarray-size-k/](https://www.geeksforgeeks.org/find-maximum-minimum-sum-subarray-size-k/)

**Difficulty:** Easy (GFG)

**Hint/Core Idea:**
Basic fixed-size sliding window.
1. Calculate the sum of the first `k` elements. This is the initial `max_sum` and `current_sum`.
2. Iterate from the `k`-th element to the end of the array.
3. In each iteration, update `current_sum` by adding the current element and subtracting the element that is sliding out of the window (`nums[i-k]`).
4. Update `max_sum = max(max_sum, current_sum)`.

**Tags:** `Array`, `Sliding Window`

---
## Problem Description (from GeeksforGeeks)

<!-- Placeholder for the full problem description from GFG.
     Copy the problem description here from the GFG page for easy reference.
     Example: Given an array of integers and a number k, find the maximum sum of a subarray of size k.
-->


## Solution Skeleton (Python)

```python
from typing import List

class Solution:
    def maxSumSubarray(self, nums: List[int], k: int) -> int:
        n = len(nums)
        if n < k or k <= 0:
            # Or raise an error, or return appropriate value like float('-inf')
            return 0 

        current_sum = sum(nums[0:k])
        max_so_far = current_sum

        for i in range(k, n):
            current_sum = current_sum - nums[i-k] + nums[i]
            if current_sum > max_so_far:
                max_so_far = current_sum
        
        return max_so_far

# Example Usage (optional, for testing):
# sol = Solution()
# print(sol.maxSumSubarray([1, 4, 2, 10, 2, 3, 1, 0, 20], 4)) # Expected: 24 (10+2+3+1+0 -> 2+3+1+0=6, 3+1+0+20=24)
# print(sol.maxSumSubarray([100, 200, 300, 400], 2))        # Expected: 700 (300+400)
# print(sol.maxSumSubarray([2, 3], 3))                      # Expected: 0 (or error, as k > n)
```
---
