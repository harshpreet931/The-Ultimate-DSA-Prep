# Binary Search

## Overview

Binary Search is a highly efficient searching algorithm that works on **sorted arrays** (or lists). It follows a divide and conquer approach by repeatedly dividing the search interval in half. If the value of the search key is less than the item in the middle of the interval, narrow the interval to the lower half. Otherwise, narrow it to the upper half. This process is repeated until the value is found or the interval is empty.

## Algorithm Steps

1.  **Initialization:**
    *   Let `low` be the starting index of the array (usually 0).
    *   Let `high` be the ending index of the array (usually `length - 1`).
2.  **Iteration/Recursion:**
    *   While `low <= high`:
        a.  Calculate the middle index: `mid = low + (high - low) / 2`. (This avoids potential overflow compared to `(low + high) / 2`).
        b.  Compare the target value with the element at `arr[mid]`:
            i.  If `arr[mid] == target`, the element is found. Return `mid`.
            ii. If `arr[mid] < target`, the target must be in the right half. Update `low = mid + 1`.
            iii.If `arr[mid] > target`, the target must be in the left half. Update `high = mid - 1`.
3.  **Element Not Found:**
    *   If the loop finishes (i.e., `low > high`), the target element is not present in the array. Return an indicator (e.g., -1, false).

## Key Properties

*   **Requires Sorted Data:** Binary search only works correctly on sorted collections.
*   **Logarithmic Time Complexity:** Due to the halving of the search space in each step.
*   **Efficient:** Significantly faster than linear search for large datasets.

## Time and Space Complexity

*   **Time Complexity:**
    *   **Worst Case:** O(log n)
    *   **Average Case:** O(log n)
    *   **Best Case:** O(1) (if the target is the middle element on the first try)
*   **Space Complexity:**
    *   **Iterative Implementation:** O(1)
    *   **Recursive Implementation:** O(log n) (due to recursion call stack)

## Variations and Applications

*   **Finding First/Last Occurrence:** Modify binary search to find the first or last occurrence of a target value if duplicates exist.
*   **Finding Smallest Element Greater Than/Equal To Target (Ceiling):**
*   **Finding Largest Element Less Than/Equal To Target (Floor):**
*   **Searching in Rotated Sorted Arrays:** Adapt binary search to handle arrays that are sorted but then rotated.
*   **Searching in "Answer Space":** Binary search can be applied to find an answer within a range of possible values if a monotonic condition (predicate function) exists. For example, finding the minimum capacity to ship packages within D days, or finding the square root of a number.
*   **Lower Bound / Upper Bound:** Similar to `std::lower_bound` and `std::upper_bound` in C++.

## Implementations

*   [Python](./Implementations/Python/)
*   [Java](./Implementations/Java/)
*   [C++](./Implementations/Cpp/)
*   [JavaScript](./Implementations/JavaScript/)

*(Contributors: Please add iterative and recursive implementations, and examples of common variations.)*

## Common Problems

*   Search in Rotated Sorted Array
*   Find First and Last Position of Element in Sorted Array
*   Find Minimum in Rotated Sorted Array
*   Median of Two Sorted Arrays (can involve binary search concepts)
*   Search a 2D Matrix
*   Find Peak Element
*   Sqrt(x)
*   Capacity To Ship Packages Within D Days
*   Koko Eating Bananas
*   ... (add more problems where binary search on answer or modified binary search is applicable)

## Further Reading & Resources

*   [Link to external article/video 1 on Binary Search basics]
*   [Link to external article/video 2 on Advanced Binary Search applications (e.g., on answer space)]
