# Disjoint Set Union (DSU) / Union-Find

## Overview

A Disjoint Set Union (DSU), also known as Union-Find or Merge-Find set, is a data structure that keeps track of a set of elements partitioned into a number of disjoint (non-overlapping) subsets. It provides two main operations:

1.  **`find(i)`:** Determine which subset an element `i` is in. This can be used for checking if two elements are in the same subset. It typically returns a "representative" or "parent" item of that set.
2.  **`union(i, j)`:** Join two subsets (the one containing `i` and the one containing `j`) into a single subset.

## Key Concepts

*   **Sets and Representatives:** Each subset is identified by a unique representative, which is one of its members (often the root of a tree representing the set).
*   **Forest Representation:** DSU is commonly implemented as a collection of trees (a forest), where each tree represents a set. The root of the tree is the representative of the set.
*   **Parent Array:** A `parent` array is used where `parent[i]` stores the parent of element `i`. If `parent[i] == i`, then `i` is the root (representative) of its set.

## Operations and Optimizations

### Basic Implementation

*   **`find(i)`:**
    ```
    while parent[i] != i:
        i = parent[i]
    return i
    ```
*   **`union(i, j)`:**
    ```
    root_i = find(i)
    root_j = find(j)
    if root_i != root_j:
        parent[root_j] = root_i // or parent[root_i] = root_j
    ```

### Optimizations

1.  **Path Compression:**
    During a `find(i)` operation, after finding the root `r`, make all nodes on the path from `i` to `r` point directly to `r`. This flattens the tree structure.
    ```python
    def find(i):
        if parent[i] == i:
            return i
        parent[i] = find(parent[i]) # Path compression
        return parent[i]
    ```

2.  **Union by Rank (or Union by Size):**
    When performing a `union(i, j)`, make the root of the smaller tree (in terms of rank/height or size/number of nodes) point to the root of the larger tree. This helps keep the trees flatter.
    *   **Union by Rank:** Keep track of the "rank" (an upper bound on the height) of each tree. Attach the tree with smaller rank to the root of the tree with larger rank. If ranks are equal, pick one as parent and increment its rank.
    *   **Union by Size:** Keep track of the "size" (number of elements) of each set. Attach the tree representing the smaller set to the root of the tree representing the larger set. Update the size of the new parent.

## Time Complexity

With both Path Compression and Union by Rank/Size optimizations:
*   **`find(i)`:** Nearly constant time on average, specifically O(α(N)), where α(N) is the inverse Ackermann function. α(N) is extremely slow-growing and is less than 5 for any practical value of N.
*   **`union(i, j)`:** Also O(α(N)).

Without optimizations, the complexity can be O(N) for operations in the worst case (e.g., forming a linked-list like tree).

## Space Complexity

*   O(N) for the `parent` array and optionally `rank`/`size` arrays.

## Implementations

*   [Python](./Implementations/Python/)
*   [Java](./Implementations/Java/)
*   [C++](./Implementations/Cpp/)
*   [JavaScript](./Implementations/JavaScript/)

*(Contributors: Please add implementations with path compression and union by rank/size.)*

## Common Applications & Problems

*   **Kruskal's Algorithm for Minimum Spanning Tree:** To detect if adding an edge forms a cycle.
*   **Detecting Cycles in an Undirected Graph:** If `find(u) == find(v)` for an edge `(u,v)` before unioning them, a cycle exists.
*   **Connected Components:** Finding connected components in an undirected graph. Iterate through edges, unioning connected vertices. The number of disjoint sets remaining is the number of connected components.
*   **Network Connectivity:** Determining if two nodes in a network are connected.
*   **Image Processing:** Grouping pixels.
*   Number of Connected Components in an Undirected Graph (LeetCode)
*   Redundant Connection (LeetCode)
*   Accounts Merge (LeetCode)
*   Friend Circles / Number of Provinces (LeetCode)
*   ... (add more problems)

## Further Reading & Resources

*   [Link to external article/video 1 on DSU basics]
*   [Link to external article/video 2 on Path Compression and Union by Rank/Size]
