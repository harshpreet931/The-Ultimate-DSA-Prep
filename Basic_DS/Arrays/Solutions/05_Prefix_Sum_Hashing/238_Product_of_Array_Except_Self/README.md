# Product of Array Except Self (LC 238)

**Link:** [https://leetcode.com/problems/product-of-array-except-self/](https://leetcode.com/problems/product-of-array-except-self/)

**Difficulty:** Medium

**Hint/Core Idea:**
The problem asks to compute an array `answer` where `answer[i]` is the product of all elements of `nums` except `nums[i]`. This must be done without using division and in O(n) time.

**O(n) space approach (using prefix and suffix product arrays):**
1. Create `prefix_products` array: `prefix_products[i]` is the product of `nums[0...i-1]`.
2. Create `suffix_products` array: `suffix_products[i]` is the product of `nums[i+1...n-1]`.
3. `answer[i] = prefix_products[i] * suffix_products[i]`.
   (Handle edge cases for `prefix_products[0]` and `suffix_products[n-1]` which would be 1).

**O(1) space approach (using the output array for one pass and a variable for the other):**
1. Initialize `answer` array of the same size as `nums`, with all elements set to 1.
2. **First pass (left to right):** Calculate prefix products.
   - `prefix_prod = 1`
   - For `i` from `0` to `n-1`:
     - `answer[i] = prefix_prod`
     - `prefix_prod *= nums[i]`
3. **Second pass (right to left):** Calculate suffix products and multiply with existing prefix products in `answer`.
   - `suffix_prod = 1`
   - For `i` from `n-1` down to `0`:
     - `answer[i] *= suffix_prod`
     - `suffix_prod *= nums[i]`
Return `answer`.

**Tags:** `Array`, `Prefix Sum`

---
## Problem Description (from LeetCode)

<!-- Placeholder for the full problem description from LeetCode.
     Copy the problem description here from the LeetCode page for easy reference.
     Example: Given an integer array nums, return an array answer such that answer[i] is equal to the product of all the elements of nums except nums[i]. The product of any prefix or suffix of nums is guaranteed to fit in a 32-bit integer. You must write an algorithm that runs in O(n) time and without using the division operation.
-->


## Solution Skeleton (Python)

```python
from typing import List

class Solution:
    def productExceptSelf(self, nums: List[int]) -> List[int]:
        # TODO: Implement solution
        pass

# Example Usage (optional, for testing):
# sol = Solution()
# print(sol.productExceptSelf([1,2,3,4])) # Expected: [24,12,8,6]
# print(sol.productExceptSelf([-1,1,0,-3,3])) # Expected: [0,0,9,0,0]
```
---
