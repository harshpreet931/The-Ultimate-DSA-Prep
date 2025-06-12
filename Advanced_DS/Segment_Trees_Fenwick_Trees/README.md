# Segment Trees & Fenwick Trees (BIT)

## Segment Trees

### Overview

A Segment Tree is a versatile tree-based data structure used for storing information about intervals or segments. Each node in the segment tree represents an interval, and it typically stores some aggregate value (like sum, min, max) for that interval. It allows for efficient querying of range statistics and updating individual elements.

### Key Concepts

*   **Tree Structure:** A binary tree where:
    *   Leaf nodes represent individual elements of an input array.
    *   Internal nodes represent the union of the intervals of their children. The value stored in an internal node is an aggregation of the values of its children (e.g., sum of children's sums).
*   **Construction:** Built recursively. The root covers the entire array range `[0, n-1]`. A node covering range `[L, R]` has children covering `[L, mid]` and `[mid+1, R]`, where `mid = (L+R)/2`. Construction takes O(n) time.
*   **Range Query:** To query an aggregate over a range `[queryL, queryR]`:
    *   Start from the root.
    *   If the current node's interval is completely within `[queryL, queryR]`, return its stored value.
    *   If the current node's interval does not overlap with `[queryL, queryR]`, return an identity value (e.g., 0 for sum, infinity for min).
    *   Otherwise, recursively query the left and right children and combine their results.
    *   Time Complexity: O(log n).
*   **Point Update:** To update an element `arr[index] = newValue`:
    *   Update the corresponding leaf node.
    *   Recursively update all ancestor nodes up to the root by re-calculating their aggregate values.
    *   Time Complexity: O(log n).
*   **Lazy Propagation (for Range Updates):**
    *   Efficiently handle updates over a range (e.g., add `val` to all elements in `[updateL, updateR]`).
    *   Instead of updating all elements in O(n), "lazy" tags are stored at nodes. These tags indicate pending updates for the node's interval.
    *   When a node with a lazy tag is visited (either for query or further update), the tag is pushed down to its children, and the current node's value is updated.
    *   Range Update with Lazy Propagation: O(log n).

### Applications

*   Range Sum Queries (RSQ)
*   Range Minimum/Maximum Queries (RMQ)
*   Range Frequency Queries
*   Problems involving intervals and dynamic updates.

---

## Fenwick Trees (Binary Indexed Trees - BIT)

### Overview

A Fenwick Tree, or Binary Indexed Tree (BIT), is a data structure that can efficiently update elements and calculate prefix sums (or other associative, invertible operations) in an array of numbers. It's particularly space-efficient (O(n)) and simpler to implement than segment trees for prefix sum type queries.

### Key Concepts

*   **Implicit Tree Structure:** The tree structure is implicit, represented by an array (let's call it `bit_array`).
*   **Responsibility:** `bit_array[idx]` stores the sum of a certain range of the original array. The range depends on the last set bit of `idx`. Specifically, `bit_array[idx]` stores the sum of elements from `(idx - (idx & -idx) + 1)` to `idx` of the original array. (`idx & -idx` gives the value of the last set bit).
*   **Update Operation (`update(index, delta)`):** To add `delta` to `arr[index]` (0-indexed original array, 1-indexed BIT):
    *   `index++` (to convert to 1-based indexing for BIT).
    *   While `index <= n` (size of BIT):
        *   `bit_array[index] += delta`
        *   `index += (index & -index)` (move to the next responsible index)
    *   Time Complexity: O(log n).
*   **Query Operation (`query(index)` or `getPrefixSum(index)`):** To get sum of `arr[0...index]` (0-indexed original array, 1-indexed BIT):
    *   `index++` (to convert to 1-based indexing).
    *   `sum = 0`
    *   While `index > 0`:
        *   `sum += bit_array[index]`
        *   `index -= (index & -index)` (move to the previous responsible index)
    *   Return `sum`.
    *   Time Complexity: O(log n).
*   **Range Sum Query `sum(L, R)`:** `getPrefixSum(R) - getPrefixSum(L-1)`.

### Construction

*   Initialize `bit_array` with zeros.
*   For each element `arr[i]` in the original array, call `update(i, arr[i])`.
*   Total construction time: O(n log n).
*   A faster O(n) construction method exists by directly calculating `bit_array` values.

### Applications

*   Prefix Sum Queries.
*   Range Sum Queries.
*   Point Updates.
*   Counting inversions (with modifications).
*   Problems requiring dynamic prefix/range aggregations.

## Segment Tree vs. Fenwick Tree

| Feature             | Segment Tree                                  | Fenwick Tree (BIT)                             |
|---------------------|-----------------------------------------------|------------------------------------------------|
| **Complexity**      | Query: O(log n), Update: O(log n)             | Query: O(log n), Update: O(log n)              |
| **Range Operations**| Versatile (sum, min, max, etc.)               | Primarily for prefix sums/invertible operations |
| **Range Updates**   | Requires Lazy Propagation (more complex)      | Can be extended for range updates (more complex) but not as naturally. |
| **Implementation**  | More complex, recursive                       | Simpler, iterative, less code                 |
| **Space**           | O(n) (typically 2n or 4n array size)        | O(n) (array of size n+1)                     |
| **Constant Factors**| Generally larger than BIT                     | Smaller constant factors, often faster in practice for its specific use cases. |
| **Flexibility**     | More flexible for various range queries       | More specialized                               |

## Implementations

*   **Segment Tree:**
    *   [Python](./Implementations/Python/segment_tree.py)
    *   [Java](./Implementations/Java/SegmentTree.java)
    *   [C++](./Implementations/Cpp/segment_tree.cpp)
    *   [JavaScript](./Implementations/JavaScript/segmentTree.js)
*   **Fenwick Tree (BIT):**
    *   [Python](./Implementations/Python/fenwick_tree.py)
    *   [Java](./Implementations/Java/FenwickTree.java)
    *   [C++](./Implementations/Cpp/fenwick_tree.cpp)
    *   [JavaScript](./Implementations/JavaScript/fenwickTree.js)

*(Contributors: Please add implementations, including lazy propagation for Segment Trees if possible.)*

## Further Reading & Resources

*   [Segment Tree (CP-Algorithms)](https://cp-algorithms.com/data_structures/segment_tree.html)
*   [Fenwick Tree (CP-Algorithms)](https://cp-algorithms.com/data_structures/fenwick.html)
*   [Segment Tree (GeeksforGeeks)](https://www.geeksforgeeks.org/segment-tree-set-1-sum-of-given-range/)
*   [Fenwick Tree (GeeksforGeeks)](https://www.geeksforgeeks.org/binary-indexed-tree-or-fenwick-tree-2/)
