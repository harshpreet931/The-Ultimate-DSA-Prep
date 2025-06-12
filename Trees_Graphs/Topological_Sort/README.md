# Topological Sort

## Overview

Topological sorting for a Directed Acyclic Graph (DAG) is a linear ordering of its vertices such that for every directed edge `u -> v` from vertex `u` to vertex `v`, vertex `u` comes before vertex `v` in the ordering.

**Key Points:**
*   Topological sort is only possible if the graph is a **Directed Acyclic Graph (DAG)**. If the graph contains a cycle, a topological sort is not possible.
*   The ordering is not unique if there are multiple valid sequences.
*   It's often used to represent dependencies, like task scheduling, course prerequisites, or compilation order.

## Algorithms for Topological Sort

### 1. Kahn's Algorithm (BFS-based)

**Idea:** Iteratively find nodes with an in-degree of 0, add them to the sorted list, and remove their outgoing edges.
1.  Compute the in-degree (number of incoming edges) for each vertex.
2.  Initialize a queue and add all vertices with an in-degree of 0 to it.
3.  Initialize an empty list `topological_order` to store the sorted vertices.
4.  While the queue is not empty:
    a.  Dequeue a vertex `u` from the queue and add it to `topological_order`.
    b.  For each neighbor `v` of `u`:
        i.  Decrement the in-degree of `v`.
        ii. If the in-degree of `v` becomes 0, enqueue `v`.
5.  If the count of visited vertices in `topological_order` is not equal to the total number of vertices in the graph, then the graph has a cycle, and a topological sort is not possible. Otherwise, `topological_order` contains a valid topological sort.

**Time Complexity:** O(V + E) (where V is vertices, E is edges)
**Space Complexity:** O(V + E) (for graph representation, in-degree array, queue)

### 2. DFS-based Algorithm

**Idea:** Perform a DFS traversal. The topological sort is the reverse of the post-order traversal (i.e., when a node finishes all its recursive calls).
1.  Initialize an empty list `topological_order` and a set/array `visited` to keep track of visited nodes. Also, maintain a `recursion_stack` set/array to detect cycles.
2.  For each vertex `u` in the graph:
    *   If `u` is not visited, call `DFS_Util(u, visited, recursion_stack, topological_order)`.
3.  The `topological_order` list, when reversed, gives a valid topological sort.

**`DFS_Util(u, visited, recursion_stack, topological_order)`:**
1.  Mark `u` as visited and add `u` to `recursion_stack`.
2.  For each neighbor `v` of `u`:
    a.  If `v` is not visited, recursively call `DFS_Util(v, ...)`. If this call detects a cycle, propagate the cycle detection.
    b.  Else if `v` is in `recursion_stack`, then a cycle is detected.
3.  Remove `u` from `recursion_stack`.
4.  Add `u` to the front of `topological_order` (or add to end and reverse later).

**Time Complexity:** O(V + E)
**Space Complexity:** O(V + E) (for graph, visited array, recursion stack)

## Implementations

*   [Python](./Implementations/Python/)
*   [Java](./Implementations/Java/)
*   [C++](./Implementations/Cpp/)
*   [JavaScript](./Implementations/JavaScript/)

*(Contributors: Please add implementations for both Kahn's algorithm and the DFS-based algorithm.)*

## Common Applications & Problems

*   **Task Scheduling:** Ordering tasks where some tasks must be completed before others.
*   **Course Prerequisites:** Determining the order in which courses must be taken.
*   **Dependency Resolution:** In software build systems or package managers.
*   **Spreadsheet Evaluation:** Determining the order to calculate cell values.
*   **Cycle Detection in Directed Graphs:** Both algorithms can be adapted to detect cycles.
*   Course Schedule (LeetCode)
*   Course Schedule II (LeetCode)
*   Alien Dictionary (LeetCode)
*   ... (add more problems)

## Further Reading & Resources

*   [Link to external article/video 1 on Kahn's Algorithm]
*   [Link to external article/video 2 on DFS-based Topological Sort]
