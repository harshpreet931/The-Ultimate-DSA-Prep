# Graphs (DFS & BFS)

## Overview

A graph is a non-linear data structure consisting of a set of **vertices** (or nodes) and a set of **edges** that connect pairs of vertices. Graphs are used to represent networks, relationships, and various other interconnected systems.

*   **Vertices (V):** The fundamental units of the graph.
*   **Edges (E):** Connections between pairs of vertices.
    *   **Undirected Edge:** A two-way connection (e.g., `(u, v)` is the same as `(v, u)`).
    *   **Directed Edge (Arc):** A one-way connection (e.g., `(u, v)` goes from `u` to `v`).
*   **Weighted Edge:** An edge with an associated numerical value (weight or cost).

## Graph Representations

1.  **Adjacency List:**
    *   An array (or map) where each index `i` (representing vertex `i`) stores a list of vertices adjacent to `i`.
    *   Space Complexity: O(V + E)
    *   Pros: Space-efficient for sparse graphs. Easy to iterate over neighbors.
    *   Cons: Checking for a specific edge `(u, v)` can take O(degree(u)) time.
2.  **Adjacency Matrix:**
    *   A V x V matrix where `matrix[i][j] = 1` (or weight) if there's an edge from vertex `i` to `j`, and `0` (or infinity) otherwise.
    *   Space Complexity: O(V^2)
    *   Pros: Fast to check for a specific edge `(u, v)` (O(1)).
    *   Cons: Space-inefficient for sparse graphs. Iterating over neighbors takes O(V) time.

## Graph Traversal Algorithms

Traversal means visiting all the nodes of a graph.

### 1. Depth-First Search (DFS)

Explores as far as possible along each branch before backtracking. It uses a stack (often implicitly via recursion).

**Algorithm:**
1.  Start at a given vertex `s`. Mark `s` as visited.
2.  For each unvisited neighbor `v` of `s`:
    *   Recursively call DFS on `v`.
(If the graph is disconnected, DFS must be called for each unvisited starting node).

**Key Features:**
*   Can be used to find connected components.
*   Detects cycles (if a visited node is encountered that is not an immediate parent in the DFS tree).
*   Used in topological sorting.
*   Pathfinding (finds *a* path, not necessarily the shortest).

**Time Complexity:** O(V + E) (using adjacency list)
**Space Complexity:** O(V) (for recursion stack or explicit stack, and visited array)

### 2. Breadth-First Search (BFS)

Explores all neighbor nodes at the present depth prior to moving on to nodes at the next depth level. It uses a queue.

**Algorithm:**
1.  Start at a given vertex `s`. Mark `s` as visited and enqueue `s`.
2.  While the queue is not empty:
    *   Dequeue a vertex `u`.
    *   For each unvisited neighbor `v` of `u`:
        *   Mark `v` as visited.
        *   Enqueue `v`.
(If the graph is disconnected, BFS must be called for each unvisited starting node).

**Key Features:**
*   Finds the shortest path in terms of number of edges in unweighted graphs.
*   Can be used to find connected components.
*   Level-order traversal of a tree is a form of BFS.

**Time Complexity:** O(V + E) (using adjacency list)
**Space Complexity:** O(V) (for queue and visited array, queue can hold up to V nodes in worst case)

## Implementations

*   [Python](./Implementations/Python/)
*   [Java](./Implementations/Java/)
*   [C++](./Implementations/Cpp/)
*   [JavaScript](./Implementations/JavaScript/)

*(Contributors: Please add implementations for both DFS and BFS using adjacency lists and/or matrices.)*

## Common Applications & Problems

*   **DFS Applications:**
    *   Finding connected components.
    *   Topological sorting.
    *   Detecting cycles in a graph.
    *   Solving puzzles like mazes.
*   **BFS Applications:**
    *   Finding the shortest path in unweighted graphs.
    *   Web crawlers.
    *   Finding connected components.
    *   Network broadcasting.
*   **Problems:**
    *   Number of Islands
    *   Clone Graph
    *   Course Schedule (Cycle detection / Topological Sort)
    *   Word Ladder (Shortest path)
    *   Rotting Oranges
    *   Pacific Atlantic Water Flow
    *   ... (add more problems)

*(Contributors: Please add links to problem statements and solutions.)*

## Further Reading & Resources

*   [Link to external article/video 1 on DFS]
*   [Link to external article/video 2 on BFS]
*   [Link to external article/video 3 on Graph Representations]
