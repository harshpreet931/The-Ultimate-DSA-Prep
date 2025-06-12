# Interpolation Search & Ternary Search

## Interpolation Search

### Overview

Interpolation Search is an improvement over Binary Search for instances where the values in a sorted array are **uniformly distributed**. While Binary Search always goes to the middle element to check, Interpolation Search may go to different locations according to the value of the key being searched. For example, if the value of the key is closer to the last element, interpolation search is likely to start search toward the end side.

### Formula for Probing Position

The position `pos` is calculated using the formula:
`pos = low + [( (key - arr[low]) * (high - low) ) / ( arr[high] - arr[low] )]`

Where:
*   `arr`: The sorted array.
*   `key`: The element to be searched.
*   `low`: Starting index in `arr`.
*   `high`: Ending index in `arr`.

### Algorithm Steps

1.  **Initialization:** `low = 0`, `high = n - 1`.
2.  **Loop:** While `low <= high` AND `key >= arr[low]` AND `key <= arr[high]`:
    a.  If `low == high`:
        i.  If `arr[low] == key`, return `low`.
        ii. Else, return -1 (not found).
    b.  Calculate `pos` using the interpolation formula.
    c.  If `arr[pos] == key`, return `pos`.
    d.  If `arr[pos] < key`, the key is in the upper part: `low = pos + 1`.
    e.  If `arr[pos] > key`, the key is in the lower part: `high = pos - 1`.
3.  **Element Not Found:** Return -1.

### Time and Space Complexity

*   **Time Complexity:**
    *   **Average Case (for uniformly distributed data):** O(log log n)
    *   **Worst Case (e.g., non-uniform distribution, exponential values):** O(n)
*   **Space Complexity:** O(1) for iterative implementation.

### When to Use

*   When the data is sorted and uniformly distributed.
*   When search operations are significantly more frequent than updates.

---

## Ternary Search

### Overview

Ternary Search is a divide and conquer searching algorithm that works on **sorted arrays**. It is similar to binary search but divides the array into three parts instead of two. It is also used to find the maximum or minimum of a **unimodal function**.

### Algorithm Steps (for sorted array search)

1.  **Initialization:** `low = 0`, `high = n - 1`.
2.  **Loop:** While `low <= high`:
    a.  Calculate `mid1 = low + (high - low) / 3`.
    b.  Calculate `mid2 = high - (high - low) / 3`.
    c.  Compare `key` with `arr[mid1]`:
        i.  If `arr[mid1] == key`, return `mid1`.
    d.  Compare `key` with `arr[mid2]`:
        i.  If `arr[mid2] == key`, return `mid2`.
    e.  Determine which third to narrow down to:
        i.  If `key < arr[mid1]`, then `high = mid1 - 1`.
        ii. Else if `key > arr[mid2]`, then `low = mid2 + 1`.
        iii.Else (key is between `arr[mid1]` and `arr[mid2]`), then `low = mid1 + 1` and `high = mid2 - 1`.
3.  **Element Not Found:** Return -1.

### Algorithm Steps (for finding max/min of a unimodal function `f(x)`)

1.  **Initialization:** `low`, `high` define the search range.
2.  **Loop (for a fixed number of iterations or until `high - low` is small):**
    a.  `m1 = low + (high - low) / 3`
    b.  `m2 = high - (high - low) / 3`
    c.  If `f(m1) < f(m2)` (for finding maximum; use `>` for minimum):
        `low = m1`
    d.  Else:
        `high = m2`
3.  The maximum/minimum is approximately at `f((low + high) / 2)`.

### Time and Space Complexity (for sorted array search)

*   **Time Complexity:** O(log<sub>3</sub> n). While the base of the logarithm is different, it's still asymptotically O(log n). Binary search is generally preferred for sorted arrays due to fewer comparisons per iteration and simpler logic.
*   **Space Complexity:** O(1) for iterative, O(log n) for recursive.

### When to Use

*   **Finding Extrema of Unimodal Functions:** This is the primary use case where ternary search shines over binary search. A unimodal function is a function that, over a given range, has only one peak (maximum) or valley (minimum).
*   Less common for searching in sorted arrays because binary search is usually more efficient due to simpler comparisons and a better constant factor.

## Implementations

*   **Interpolation Search:**
    *   [Python](./Implementations/Python/interpolation_search.py)
    *   [Java](./Implementations/Java/InterpolationSearch.java)
    *   [C++](./Implementations/Cpp/interpolation_search.cpp)
    *   [JavaScript](./Implementations/JavaScript/interpolationSearch.js)
*   **Ternary Search:**
    *   [Python](./Implementations/Python/ternary_search.py)
    *   [Java](./Implementations/Java/TernarySearch.java)
    *   [C++](./Implementations/Cpp/ternary_search.cpp)
    *   [JavaScript](./Implementations/JavaScript/ternarySearch.js)

*(Contributors: Please add implementations for both search types.)*

## Further Reading & Resources

*   [Interpolation Search (GeeksforGeeks)](https://www.geeksforgeeks.org/interpolation-search/)
*   [Ternary Search (GeeksforGeeks)](https://www.geeksforgeeks.org/ternary-search/)
*   [Ternary Search for Unimodal Functions (CP-Algorithms)](https://cp-algorithms.com/num_methods/ternary_search.html)
