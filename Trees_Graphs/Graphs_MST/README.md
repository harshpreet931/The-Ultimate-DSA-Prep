# Graphs (Minimum Spanning Tree - MST)

## Overview

A Minimum Spanning Tree (MST) or minimum weight spanning tree is a subset of the edges of a connected, edge-weighted undirected graph that connects all the vertices together, without any cycles and with the minimum possible total edge weight.

In simpler terms, an MST is a tree formed from a subset of the edges of a given undirected graph, such that:
1.  It spans all vertices of the original graph (i.e., it's a spanning tree).
2.  The sum of the weights of the edges in the tree is minimized.

MSTs are only defined for connected, undirected, weighted graphs. If a graph is not connected, one can find an MST for each connected component (forming a Minimum Spanning Forest).

## Key Concepts

*   **Spanning Tree:** A subgraph that is a tree and connects all the vertices together. A single graph can have many different spanning trees.
*   **Minimum Total Weight:** Among all possible spanning trees, the MST has the smallest sum of edge weights.
*   **Cut Property (or Cut Theorem):** For any cut (a partition of the graph's vertices into two disjoint sets), if the weight of an edge `(u,v)` is strictly smaller than the weights of all other edges with one endpoint in one set and the other endpoint in the other set, then this edge belongs to all MSTs of the graph.
*   **Cycle Property:** For any cycle in the graph, if the weight of an edge in the cycle is strictly larger than the weights of all other edges in the cycle, then this edge cannot belong to any MST.

## Algorithms for Finding MST

### 1. Kruskal's Algorithm

**Idea:** Greedily add edges with the smallest weights that do not form a cycle.
1.  Sort all edges in non-decreasing order of their weights.
2.  Initialize an empty set for the MST.
3.  Iterate through the sorted edges:
    *   If adding the current edge to the MST set does not form a cycle, add it.
    *   Use a Disjoint Set Union (DSU) data structure to efficiently check for cycles. (If both vertices of an edge are already in the same set, adding the edge would form a cycle).
4.  Repeat until V-1 edges are added to the MST (where V is the number of vertices).

**Time Complexity:** O(E log E) or O(E log V) - dominated by sorting edges. DSU operations are nearly constant time (O(α(V)), where α is the inverse Ackermann function).
**Space Complexity:** O(V + E) (for storing graph, edges, and DSU structure).

### 2. Prim's Algorithm

**Idea:** Grow the MST from an arbitrary starting vertex. At each step, add the minimum weight edge that connects a vertex in the current MST to a vertex outside the MST.
1.  Initialize an empty MST.
2.  Choose an arbitrary starting vertex `s`.
3.  Maintain a set of visited vertices (initially just `s`) and a way to find the minimum weight edge connecting a visited vertex to an unvisited vertex (often using a Min-Priority Queue).
4.  While not all vertices are in the MST:
    *   Select the minimum weight edge `(u,v)` such that `u` is in the MST and `v` is not.
    *   Add `v` to the MST and the edge `(u,v)` to the MST edges.
    *   Update the priority queue with edges from `v` to its unvisited neighbors.

**Time Complexity:**
*   O(E log V) using a binary heap for the priority queue.
*   O(E + V log V) using a Fibonacci heap.
*   O(V^2) if using an adjacency matrix and searching for min edge naively (suitable for dense graphs).
**Space Complexity:** O(V + E) (for storing graph, priority queue, etc.).

## Implementations

*   [Python](./Implementations/Python/)
*   [Java](./Implementations/Java/)
*   [C++](./Implementations/Cpp/)
*   [JavaScript](./Implementations/JavaScript/)

*(Contributors: Please add implementations for both Kruskal's and Prim's algorithms.)*

## Common Applications & Problems

*   Network design (e.g., laying cables for telecommunications, power grids, water networks to minimize cost).
*   Approximation algorithms for NP-hard problems (e.g., Traveling Salesperson Problem).
*   Cluster analysis (e.g., k-means clustering).
*   Image segmentation.
*   Min Cost to Connect All Points (LeetCode)
*   Connecting Cities With Minimum Cost (LeetCode)
*   ... (add more problems)

## Further Reading & Resources

*   [Link to external article/video 1 on Kruskal's Algorithm]
*   [Link to external article/video 2 on Prim's Algorithm]
*   [Link to external article/video 3 on Disjoint Set Union (DSU)]
