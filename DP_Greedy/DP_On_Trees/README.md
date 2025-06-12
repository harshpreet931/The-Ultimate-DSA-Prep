# Dynamic Programming on Trees (DP on Trees)

## Overview

Dynamic Programming on Trees is a technique where DP principles are applied to problems involving tree data structures. The subproblems are typically defined with respect to the subtrees rooted at each node. The solution for a node is computed based on the solutions for its children.

This often involves one or more Depth First Search (DFS) traversals. Information is passed up from children to parents (post-order traversal style) or sometimes down from parents to children (pre-order traversal style, often in a second DFS pass for re-rooting or calculating answers relative to each node).

## Key Concepts

*   **State Definition:** The DP state `dp[u]` (or `dp[u][state_variable]`) usually stores information about the optimal solution or count for the subtree rooted at node `u`, possibly under certain conditions indicated by `state_variable`.
    *   `state_variable` could represent:
        *   Whether node `u` is included/excluded in a set (e.g., Maximum Independent Set).
        *   The color of node `u` (e.g., tree coloring problems).
        *   Information about paths passing through `u`.
*   **Recursive Relation (Transitions):** The DP value for a node `u` is computed using the DP values of its children `v1, v2, ... vk`.
    `dp[u] = combine(dp[v1], dp[v2], ..., dp[vk], information_about_u)`
*   **Base Cases:** Leaf nodes often serve as base cases. Their DP values are usually straightforward to compute.
*   **Traversal:** A DFS traversal is typically used. The DP values for children are computed before the parent (post-order traversal logic).

## Common Patterns and Problems

1.  **Path Problems:**
    *   **Diameter of a Tree:** Longest path between any two nodes in the tree.
        *   For each node `u`, find the two longest paths starting from `u` and going into two different subtrees of `u`. The sum of these two paths + `u` itself (if edges are counted) could be a diameter candidate passing through `u`.
        *   `dp[u]` could store the length of the longest path starting at `u` and going down into its subtree.
    *   **Longest Path from a Node:** Similar to diameter, but focused on paths starting at a specific node.
    *   **Max Path Sum (node values can be negative):** Find a path that maximizes the sum of node values.

2.  **Subtree/Vertex Property Problems:**
    *   **Maximum Independent Set on a Tree:** Find the largest set of vertices such that no two vertices are adjacent.
        *   `dp[u][0]`: Max independent set in subtree of `u`, where `u` is NOT included.
        *   `dp[u][1]`: Max independent set in subtree of `u`, where `u` IS included.
        *   `dp[u][0] = sum(max(dp[v][0], dp[v][1]))` for all children `v` of `u`.
        *   `dp[u][1] = 1 + sum(dp[v][0])` for all children `v` of `u`.
    *   **Vertex Cover:** Find the smallest set of vertices such that every edge has at least one endpoint in the set.
    *   **Tree Coloring Problems:** Count ways to color a tree with K colors under certain constraints.

3.  **Counting Problems:**
    *   **Number of paths of a certain length.**
    *   **Number of subtrees satisfying a property.**

4.  **Re-rooting Technique (Second DFS Pass):**
    *   Sometimes, after computing initial DP values (e.g., properties relative to subtrees rooted at `u`), a second DFS pass is needed to compute answers for each node as if it were the root of the entire tree.
    *   Information is passed from parent to child, combining with previously computed child-to-parent information.
    *   Example: Sum of distances from node `u` to all other nodes in the tree.

## General Approach

1.  **Define the DP State(s):** What information `dp[u][...]` needs to store for the subtree at `u`.
2.  **Identify Base Cases:** Usually leaf nodes.
3.  **Formulate Recurrence Relations:** How to compute `dp[u][...]` from `dp[child][...]`.
4.  **Perform DFS:**
    *   In the post-order traversal part of DFS (after visiting all children of `u`):
        *   Compute `dp[u][...]` using the values from its children.
    *   The final answer might be `dp[root][...]` or an aggregation of DP values.
5.  **(Optional) Second DFS for Re-rooting:** If the problem requires answers relative to each node being the "center" or "root".

## Example: Diameter of a Tree

*   `dp[u]` = length of the longest path starting at `u` and going downwards into its subtree.
*   `diameter` = global variable, updated whenever a longer path *through* a node `u` is found.
*   **DFS(u, parent):**
    1.  Initialize `longest1 = 0`, `longest2 = 0` (for paths starting at `u`).
    2.  For each child `v` of `u` (where `v != parent`):
        a.  `path_from_v = DFS(v, u)`
        b.  If `path_from_v + 1 > longest1`: `longest2 = longest1`, `longest1 = path_from_v + 1`
        c.  Else if `path_from_v + 1 > longest2`: `longest2 = path_from_v + 1`
    3.  `diameter = max(diameter, longest1 + longest2)`
    4.  Return `longest1` (this is `dp[u]`)

## Implementations

*   [Python](./Implementations/Python/)
*   [Java](./Implementations/Java/)
*   [C++](./Implementations/Cpp/)
*   [JavaScript](./Implementations/JavaScript/)

*(Contributors: Please add examples of classic DP on Tree problems.)*

## Further Reading & Resources

*   [Link to external article/video 1 on DP on Trees Introduction]
*   [Link to external article/video 2 on Diameter of a Tree using DP]
*   [Link to external article/video 3 on Re-rooting technique]
