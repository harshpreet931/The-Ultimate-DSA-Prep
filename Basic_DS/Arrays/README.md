# Arrays

## Overview

An array is a data structure consisting of a collection of elements (values or variables), each identified by at least one array index or key. An array is stored such that the position of each element can be computed from its index tuple by a mathematical formula.

## Key Concepts

*   Declaration and Initialization
*   Accessing Elements
*   Traversing Arrays
*   Common Operations (Insertion, Deletion, Search, Update)
*   Dynamic Arrays vs. Static Arrays
*   Multi-dimensional Arrays

## Time and Space Complexity

*   **Access:** O(1)
*   **Search (unsorted):** O(n)
*   **Search (sorted):** O(log n) (using binary search)
*   **Insertion (at end, if space available):** O(1)
*   **Insertion (at beginning/middle):** O(n)
*   **Deletion (at end):** O(1)
*   **Deletion (at beginning/middle):** O(n)
*   **Space Complexity:** O(n)

## Implementations

*   [Python](./Implementations/Python/)
*   [Java](./Implementations/Java/)
*   [C++](./Implementations/Cpp/)
*   [JavaScript](./Implementations/JavaScript/)

*(Contributors: Please add implementations in the respective language folders.)*

## Common Problems

This section lists curated problems from LeetCode (LC) and GeeksforGeeks (GFG) to practice Array concepts. Each problem will eventually have its own directory with solutions in various languages (e.g., `Problems/LC217_Contains_Duplicate/`).

---

**I. Basic Array Manipulation & Searching (Foundation)**

1.  **LC 217. Contains Duplicate (E):** Introduction to using hashing (sets) for quick lookups.
    -   [Problem Link](https://leetcode.com/problems/contains-duplicate/)
    -   `Solutions/LC217_Contains_Duplicate/` (placeholder for solution files)
2.  **LC 268. Missing Number (E):** Techniques like sum formula, XOR, or cyclic sort concept.
    -   [Problem Link](https://leetcode.com/problems/missing-number/)
    -   `Solutions/LC268_Missing_Number/`
3.  **LC 1. Two Sum (E):** Classic hash map application for O(n) lookup.
    -   [Problem Link](https://leetcode.com/problems/two-sum/)
    -   `Solutions/LC1_Two_Sum/`
4.  **LC 121. Best Time to Buy and Sell Stock (E):** Simple one-pass approach tracking minimum price.
    -   [Problem Link](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/)
    -   `Solutions/LC121_Best_Time_To_Buy_And_Sell_Stock/`
5.  **LC 283. Move Zeroes (E):** In-place manipulation using two pointers (different speeds).
    -   [Problem Link](https://leetcode.com/problems/move-zeroes/)
    -   `Solutions/LC283_Move_Zeroes/`
6.  **LC 88. Merge Sorted Array (E):** Merging in-place, often requires iterating backwards.
    -   [Problem Link](https://leetcode.com/problems/merge-sorted-array/)
    -   `Solutions/LC88_Merge_Sorted_Array/`
7.  **LC 189. Rotate Array (M):** Several approaches (extra array, reversal algorithm, cyclic replacements).
    -   [Problem Link](https://leetcode.com/problems/rotate-array/)
    -   `Solutions/LC189_Rotate_Array/`
8.  **LC 26. Remove Duplicates from Sorted Array (E):** In-place modification using two pointers (slow and fast).
    -   [Problem Link](https://leetcode.com/problems/remove-duplicates-from-sorted-array/)
    -   `Solutions/LC26_Remove_Duplicates_From_Sorted_Array/`
9.  **LC 27. Remove Element (E):** Similar to Remove Duplicates, in-place removal.
    -   [Problem Link](https://leetcode.com/problems/remove-element/)
    -   `Solutions/LC27_Remove_Element/`
10. **GFG - Find the element that appears once in sorted array (E/M):** Binary search modification. (Similar LC: 540. Single Element in a Sorted Array)
    -   [Problem Link](https://www.geeksforgeeks.org/find-the-element-that-appears-once-in-a-sorted-array/)
    -   `Solutions/GFG_Element_Appears_Once_Sorted/`

**II. Kadane's Algorithm & Variations**

1.  **LC 53. Maximum Subarray (E):** The classic Kadane's algorithm.
    -   [Problem Link](https://leetcode.com/problems/maximum-subarray/)
    -   `Solutions/LC53_Maximum_Subarray/`
2.  **LC 152. Maximum Product Subarray (M):** Variation of Kadane's, need to track min product too due to negatives.
    -   [Problem Link](https://leetcode.com/problems/maximum-product-subarray/)
    -   `Solutions/LC152_Maximum_Product_Subarray/`
3.  **LC 918. Maximum Sum Circular Subarray (M):** Combines Kadane's with total sum and min subarray sum concepts.
    -   [Problem Link](https://leetcode.com/problems/maximum-sum-circular-subarray/)
    -   `Solutions/LC918_Maximum_Sum_Circular_Subarray/`

**III. Two Pointers**

1.  **LC 167. Two Sum II - Input Array Is Sorted (M):** Classic two pointers (start and end) approach on sorted array.
    -   [Problem Link](https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/)
    -   `Solutions/LC167_Two_Sum_II/`
2.  **LC 15. 3Sum (M):** Combines sorting with two pointers (fix one element, find two others). Careful with duplicates.
    -   [Problem Link](https://leetcode.com/problems/3sum/)
    -   `Solutions/LC15_3Sum/`
3.  **LC 11. Container With Most Water (M):** Two pointers from ends, move the pointer with the smaller height.
    -   [Problem Link](https://leetcode.com/problems/container-with-most-water/)
    -   `Solutions/LC11_Container_With_Most_Water/`
4.  **LC 42. Trapping Rain Water (H):** Can be solved with two pointers, dynamic programming, or stack. Two pointers is elegant.
    -   [Problem Link](https://leetcode.com/problems/trapping-rain-water/)
    -   `Solutions/LC42_Trapping_Rain_Water/`
5.  **LC 977. Squares of a Sorted Array (E):** Two pointers from ends to build the result array efficiently.
    -   [Problem Link](https://leetcode.com/problems/squares-of-a-sorted-array/)
    -   `Solutions/LC977_Squares_Of_A_Sorted_Array/`
6.  **LC 75. Sort Colors (M):** Dutch National Flag problem using three pointers (low, mid, high).
    -   [Problem Link](https://leetcode.com/problems/sort-colors/)
    -   `Solutions/LC75_Sort_Colors/`
7.  **LC 80. Remove Duplicates from Sorted Array II (M):** Variation allowing k duplicates, requires slight modification of two pointers.
    -   [Problem Link](https://leetcode.com/problems/remove-duplicates-from-sorted-array-ii/)
    -   `Solutions/LC80_Remove_Duplicates_From_Sorted_Array_II/`
8.  **LC 18. 4Sum (M):** Extension of 3Sum, requires nested loops and two pointers. Handle duplicates carefully.
    -   [Problem Link](https://leetcode.com/problems/4sum/)
    -   `Solutions/LC18_4Sum/`
9.  **GFG - Pair with given sum in a sorted array (E):** Same core logic as LC 167. (This GFG link adds rotation, good variation!)
    -   [Problem Link](https://www.geeksforgeeks.org/given-a-sorted-and-rotated-array-find-if-there-is-a-pair-with-a-given-sum/)
    -   `Solutions/GFG_Pair_With_Given_Sum_Sorted_Rotated/`

**IV. Sliding Window**

1.  **GFG - Max Sum Subarray of size K (E):** Basic fixed-size sliding window. (Similar LC: Implicit in many problems)
    -   [Problem Link](https://www.geeksforgeeks.org/find-maximum-minimum-sum-subarray-size-k/)
    -   `Solutions/GFG_Max_Sum_Subarray_Size_K/`
2.  **LC 209. Minimum Size Subarray Sum (M):** Variable-size window, shrink when condition met.
    -   [Problem Link](https://leetcode.com/problems/minimum-size-subarray-sum/)
    -   `Solutions/LC209_Minimum_Size_Subarray_Sum/`
3.  **LC 3. Longest Substring Without Repeating Characters (M):** Variable-size window using a hash map/set to track characters.
    -   [Problem Link](https://leetcode.com/problems/longest-substring-without-repeating-characters/)
    -   `Solutions/LC3_Longest_Substring_Without_Repeating_Characters/`
4.  **LC 438. Find All Anagrams in a String (M):** Fixed-size window with frequency map comparison.
    -   [Problem Link](https://leetcode.com/problems/find-all-anagrams-in-a-string/)
    -   `Solutions/LC438_Find_All_Anagrams_In_A_String/`
5.  **LC 567. Permutation in String (M):** Similar to Anagrams, check if any permutation exists as a substring.
    -   [Problem Link](https://leetcode.com/problems/permutation-in-string/)
    -   `Solutions/LC567_Permutation_In_String/`
6.  **LC 76. Minimum Window Substring (H):** Classic hard sliding window, track required characters and count.
    -   [Problem Link](https://leetcode.com/problems/minimum-window-substring/)
    -   `Solutions/LC76_Minimum_Window_Substring/`
7.  **LC 424. Longest Repeating Character Replacement (M):** Sliding window where the condition involves window_size - max_freq <= k.
    -   [Problem Link](https://leetcode.com/problems/longest-repeating-character-replacement/)
    -   `Solutions/LC424_Longest_Repeating_Character_Replacement/`
8.  **LC 1004. Max Consecutive Ones III (M):** Sliding window allowing flipping K zeros.
    -   [Problem Link](https://leetcode.com/problems/max-consecutive-ones-iii/)
    -   `Solutions/LC1004_Max_Consecutive_Ones_III/`
9.  **LC 904. Fruit Into Baskets (M):** Sliding window, equivalent to longest subarray with at most 2 distinct elements.
    -   [Problem Link](https://leetcode.com/problems/fruit-into-baskets/)
    -   `Solutions/LC904_Fruit_Into_Baskets/`
10. **LC 239. Sliding Window Maximum (H):** Finding max in a fixed window efficiently, often uses a Deque.
    -   [Problem Link](https://leetcode.com/problems/sliding-window-maximum/)
    -   `Solutions/LC239_Sliding_Window_Maximum/`

**V. Prefix Sum & Hashing Combinations**

1.  **LC 303. Range Sum Query - Immutable (E):** Introduction to Prefix Sum.
    -   [Problem Link](https://leetcode.com/problems/range-sum-query-immutable/)
    -   `Solutions/LC303_Range_Sum_Query_Immutable/`
2.  **LC 560. Subarray Sum Equals K (M):** Classic application of prefix sums combined with a hash map to find sum[i] - sum[j] == k.
    -   [Problem Link](https://leetcode.com/problems/subarray-sum-equals-k/)
    -   `Solutions/LC560_Subarray_Sum_Equals_K/`
3.  **LC 523. Continuous Subarray Sum (M):** Check if subarray sum is multiple of k. Uses prefix sum modulo k and hash map.
    -   [Problem Link](https://leetcode.com/problems/continuous-subarray-sum/)
    -   `Solutions/LC523_Continuous_Subarray_Sum/`
4.  **LC 238. Product of Array Except Self (M):** Can be solved using prefix/suffix products (or division if allowed). O(1) space variation is tricky.
    -   [Problem Link](https://leetcode.com/problems/product-of-array-except-self/)
    -   `Solutions/LC238_Product_Of_Array_Except_Self/`

**VI. Intervals**

1.  **LC 56. Merge Intervals (M):** Sort intervals and merge overlaps.
    -   [Problem Link](https://leetcode.com/problems/merge-intervals/)
    -   `Solutions/LC56_Merge_Intervals/`
2.  **LC 57. Insert Interval (M):** Insert a new interval into a sorted list of non-overlapping intervals and merge if necessary.
    -   [Problem Link](https://leetcode.com/problems/insert-interval/)
    -   `Solutions/LC57_Insert_Interval/`
3.  **LC 435. Non-overlapping Intervals (M):** Greedy approach after sorting, find max number of intervals to keep (or min to remove).
    -   [Problem Link](https://leetcode.com/problems/non-overlapping-intervals/)
    -   `Solutions/LC435_Non_overlapping_Intervals/`

**VII. 2D Arrays / Matrices**

1.  **LC 73. Set Matrix Zeroes (M):** In-place modification, need to avoid immediate zeroing. Use first row/col or extra arrays as markers.
    -   [Problem Link](https://leetcode.com/problems/set-matrix-zeroes/)
    -   `Solutions/LC73_Set_Matrix_Zeroes/`
2.  **LC 54. Spiral Matrix (M):** Traverse matrix layer by layer. Careful with boundaries.
    -   [Problem Link](https://leetcode.com/problems/spiral-matrix/)
    -   `Solutions/LC54_Spiral_Matrix/`
3.  **LC 48. Rotate Image (M):** In-place rotation (transpose + reflect).
    -   [Problem Link](https://leetcode.com/problems/rotate-image/)
    -   `Solutions/LC48_Rotate_Image/`
4.  **LC 74. Search a 2D Matrix (M):** Treat the matrix as a sorted list for binary search, or search row then column.
    -   [Problem Link](https://leetcode.com/problems/search-a-2d-matrix/)
    -   `Solutions/LC74_Search_A_2D_Matrix/`
5.  **LC 240. Search a 2D Matrix II (M):** Efficient search in a row/col sorted matrix starting from top-right or bottom-left.
    -   [Problem Link](https://leetcode.com/problems/search-a-2d-matrix-ii/)
    -   `Solutions/LC240_Search_A_2D_Matrix_II/`

**VIII. Advanced / Combined Concepts**

1.  **LC 4. Median of Two Sorted Arrays (H):** Requires binary search on partitions, conceptually challenging.
    -   [Problem Link](https://leetcode.com/problems/median-of-two-sorted-arrays/)
    -   `Solutions/LC4_Median_Of_Two_Sorted_Arrays/`
2.  **LC 41. First Missing Positive (H):** Clever in-place hashing using array indices (cyclic sort variation).
    -   [Problem Link](https://leetcode.com/problems/first-missing-positive/)
    -   `Solutions/LC41_First_Missing_Positive/`
3.  **LC 287. Find the Duplicate Number (M):** Floyd's cycle-finding algorithm (like linked list cycle) or binary search on range.
    -   [Problem Link](https://leetcode.com/problems/find-the-duplicate-number/)
    -   `Solutions/LC287_Find_The_Duplicate_Number/`
4.  **LC 169. Majority Element (E):** Boyer-Moore Voting Algorithm.
    -   [Problem Link](https://leetcode.com/problems/majority-element/)
    -   `Solutions/LC169_Majority_Element/`
5.  **LC 229. Majority Element II (M):** Extension of Boyer-Moore for elements appearing > n/3 times (at most 2 such elements).
    -   [Problem Link](https://leetcode.com/problems/majority-element-ii/)
    -   `Solutions/LC229_Majority_Element_II/`
6.  **LC 128. Longest Consecutive Sequence (M):** Use a Set for O(1) lookups and intelligently check for sequence starts.
    -   [Problem Link](https://leetcode.com/problems/longest-consecutive-sequence/)
    -   `Solutions/LC128_Longest_Consecutive_Sequence/`

---
*(Contributors: Please add links to problem statements and solutions, and create solution files in the respective `Solutions/` subdirectories.)*

## Further Reading & Resources

*   [Link to external article/video 1]
*   [Link to external article/video 2]
