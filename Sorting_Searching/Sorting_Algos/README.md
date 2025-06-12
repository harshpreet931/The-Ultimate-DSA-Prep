# Sorting Algorithms

## Overview

Sorting is the process of arranging items in a sequence ordered by some criterion. Sorting algorithms are a fundamental part of computer science, used to organize data in a meaningful way, which can significantly improve the efficiency of other operations like searching.

## Key Concepts

*   **In-place vs. Out-of-place (Not-in-place):**
    *   **In-place:** Sorts the input by modifying the original array directly, using only a small, constant amount of extra space (O(1) or O(log n) for recursion stack).
    *   **Out-of-place:** Requires extra space proportional to the input size (O(n)) to store elements during sorting.
*   **Stable vs. Unstable:**
    *   **Stable:** Preserves the relative order of equal elements. If two items have the same key, their relative order in the sorted output will be the same as their relative order in the input.
    *   **Unstable:** Does not guarantee the relative order of equal elements.
*   **Comparison vs. Non-comparison Sorts:**
    *   **Comparison Sorts:** Determine the sorted order by comparing elements (e.g., Bubble Sort, Merge Sort, Quick Sort). Lower bound is O(n log n).
    *   **Non-comparison Sorts:** Use other properties of the elements (e.g., their actual values or digits) to sort them without direct comparisons (e.g., Counting Sort, Radix Sort). Can be faster than O(n log n) under certain conditions.
*   **Adaptive Sort:** Performance improves if the input is already partially sorted.

## Common Sorting Algorithms

Here's a summary of some well-known sorting algorithms:

| Algorithm        | Time Complexity (Best) | Time Complexity (Avg) | Time Complexity (Worst) | Space Complexity (Worst) | Stable | In-place | Notes                                       |
|------------------|------------------------|-----------------------|-------------------------|--------------------------|--------|----------|---------------------------------------------|
| **Bubble Sort**  | O(n)                   | O(n<sup>2</sup>)      | O(n<sup>2</sup>)        | O(1)                     | Yes    | Yes      | Simple, inefficient for large datasets.     |
| **Selection Sort**| O(n<sup>2</sup>)       | O(n<sup>2</sup>)      | O(n<sup>2</sup>)        | O(1)                     | No\*   | Yes      | Simple, inefficient.                        |
| **Insertion Sort**| O(n)                   | O(n<sup>2</sup>)      | O(n<sup>2</sup>)        | O(1)                     | Yes    | Yes      | Efficient for small or nearly sorted data.  |
| **Merge Sort**   | O(n log n)             | O(n log n)            | O(n log n)              | O(n)                     | Yes    | No       | Divide and conquer, consistent performance. |
| **Quick Sort**   | O(n log n)             | O(n log n)            | O(n<sup>2</sup>)        | O(log n) - O(n)\*\*    | No     | Yes\*\*\*| Divide and conquer, often faster in practice.|
| **Heap Sort**    | O(n log n)             | O(n log n)            | O(n log n)              | O(1)                     | No     | Yes      | Uses a binary heap.                         |
| **Counting Sort**| O(n + k)               | O(n + k)              | O(n + k)                | O(k)                     | Yes    | No       | Non-comparison, k is range of input values. |
| **Radix Sort**   | O(d * (n + k))         | O(d * (n + k))        | O(d * (n + k))          | O(n + k)                 | Yes    | No       | Non-comparison, d is digits, k is base.   |
| **Bucket Sort**  | O(n + k)               | O(n + k)              | O(n<sup>2</sup>)        | O(n + k)                 | Yes    | No       | Distributes elements into buckets.          |
| **TimSort**      | O(n)                   | O(n log n)            | O(n log n)              | O(n)                     | Yes    | Yes      | Hybrid (Merge + Insertion), Python/Java default. |
| **Shell Sort**   | O(n log n) (depends on gap) | Varies             | O(n<sup>2</sup>) (worst gap) | O(1)                | No     | Yes      | Improvement over insertion sort.            |

\* Standard Selection Sort is not stable, but can be made stable.
\*\* Quick Sort space is O(log n) for recursive stack on average, O(n) in worst case.
\*\*\* Quick Sort is typically in-place using Hoare's partition scheme. Lomuto's can also be in-place.

## Implementations

*   [Python](./Implementations/Python/)
*   [Java](./Implementations/Java/)
*   [C++](./Implementations/Cpp/)
*   [JavaScript](./Implementations/JavaScript/)

*(Contributors: Please add implementations for various sorting algorithms.)*

## When to Use Which Algorithm?

*   **Small dataset or nearly sorted:** Insertion Sort.
*   **Guaranteed O(n log n) performance, stability needed:** Merge Sort, TimSort.
*   **Fastest on average, in-place (if worst-case O(n<sup>2</sup>) is acceptable or handled):** Quick Sort.
*   **In-place, O(n log n) guaranteed (but not stable):** Heap Sort.
*   **Integers with a small range:** Counting Sort.
*   **Integers with multiple digits or fixed-length strings:** Radix Sort.
*   **Uniformly distributed data:** Bucket Sort.

## Further Reading & Resources

*   [Visualizations of Sorting Algorithms](https://www.toptal.com/developers/sorting-algorithms)
*   [Comparison of Sorting Algorithms (Wikipedia)](https://en.wikipedia.org/wiki/Sorting_algorithm#Comparison_of_algorithms)
