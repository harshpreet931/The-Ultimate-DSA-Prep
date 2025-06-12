# Strongly Connected Components (SCC)

## Overview

In a directed graph, a **Strongly Connected Component (SCC)** is a subgraph where every vertex is reachable from every other vertex within that subgraph. More formally, two vertices `u` and `v` are in the same SCC if there is a path from `u` to `v` and a path from `v` to `u`.

**Key Points:**
*   SCCs are defined for **directed graphs**.
*   Every directed graph can be uniquely partitioned into its SCCs.
*   If you contract each SCC into a single super-vertex, the resulting graph (called the **condensation graph** or **component graph**) is a Directed Acyclic Graph (DAG).

## Algorithms for Finding SCCs

### 1. Kosaraju's Algorithm

**Idea:** Uses two DFS passes. The first DFS (on the original graph) determines a processing order for vertices. The second DFS (on the transpose graph, G<sup>T</sup>) uses this order to discover SCCs one by one.

**Steps:**
1.  **First DFS (on G):**
    a.  Perform a DFS on the original graph `G`.
    b.  Keep track of the finishing times of each vertex (or simply store vertices in a stack/list in the order they finish).
2.  **Compute Transpose Graph (G<sup>T</sup>):**
    a.  Create a new graph `G^T` by reversing all the edges of `G`. If `G` has an edge `u -> v`, then `G^T` has an edge `v -> u`.
3.  **Second DFS (on G<sup>T</sup>):**
    a.  Process vertices in the decreasing order of their finishing times obtained from the first DFS (i.e., pop from the stack).
    b.  For each unvisited vertex `u` in this order, perform a DFS on `G^T` starting from `u`. All vertices visited during this DFS form one SCC.
    c.  Mark visited vertices and repeat until all vertices are processed.

**Time Complexity:** O(V + E) (Two DFS passes and graph transpose)
**Space Complexity:** O(V + E) (For graph representations, stack, visited array)

### 2. Tarjan's Algorithm

**Idea:** Uses a single DFS pass. It maintains discovery times and "low-link" values for each node to identify SCCs.

**Steps:**
1.  Initialize `discovery_time[u]` (time at which `u` is visited) and `low_link[u]` (lowest discovery time reachable from `u`, including itself, through the DFS tree possibly using one back-edge) for all vertices to infinity/unvisited.
2.  Initialize an empty stack to keep track of visited vertices in the current recursion path. Also, a boolean `on_stack[u]` to check if a vertex is on the stack.
3.  For each vertex `u` in the graph:
    *   If `u` is not visited, call `DFS_Tarjan(u)`.

**`DFS_Tarjan(u)`:**
1.  Set `discovery_time[u] = low_link[u] = time++`.
2.  Push `u` onto the stack and set `on_stack[u] = true`.
3.  For each neighbor `v` of `u`:
    a.  If `v` is not visited:
        i.  Recursively call `DFS_Tarjan(v)`.
        ii. `low_link[u] = min(low_link[u], low_link[v])`.
    b.  Else if `v` is `on_stack` (meaning `v` is an ancestor in DFS tree and `(u,v)` is a back-edge):
        i.  `low_link[u] = min(low_link[u], discovery_time[v])`.
4.  If `low_link[u] == discovery_time[u]`, then `u` is the root of an SCC.
    a.  Pop vertices from the stack until `u` is popped. All popped vertices form one SCC.
    b.  Set `on_stack` to false for these popped vertices.

**Time Complexity:** O(V + E) (Single DFS pass)
**Space Complexity:** O(V + E) (For graph, stack, visited/discovery/low-link arrays)

## Implementations

*   [Python](./Implementations/Python/)
*   [Java](./Implementations/Java/)
*   [C++](./Implementations/Cpp/)
*   [JavaScript](./Implementations/JavaScript/)

*(Contributors: Please add implementations for Kosaraju's and/or Tarjan's algorithm.)*

## Common Applications & Problems

*   **Cycle Detection:** A graph has a cycle if and only if it has an SCC with more than one vertex or an SCC with one vertex that has a self-loop.
*   **Analyzing Web Graph Structure:** Identifying communities or tightly linked clusters of web pages.
*   **Social Network Analysis:** Finding groups of people who are strongly connected.
*   **2-Satisfiability (2-SAT) Problems:** SCCs are used in solving 2-SAT instances.
*   Number of Strongly Connected Components
*   Critical Connections in a Network (Bridges, though related to undirected graphs, SCC concepts are foundational)
*   ... (add more problems)

## Further Reading & Resources

*   [Link to external article/video 1 on Kosaraju's Algorithm]
*   [Link to external article/video 2 on Tarjan's Algorithm]
*   [Link to external article/video 3 on Condensation Graphs]
