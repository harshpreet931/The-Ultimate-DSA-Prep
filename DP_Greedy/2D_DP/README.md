# 2D Dynamic Programming (2D DP)

## Overview

**2D Dynamic Programming** extends the concepts of 1D DP to problems where the state is defined by two parameters. This typically involves using a two-dimensional array (or matrix) `dp[i][j]` to store the solutions to subproblems. The value `dp[i][j]` usually represents the solution for a subproblem concerning elements up to index `i` from one input and up to index `j` from another input, or a subproblem defined by a range `[i, j]`.

## Key Concepts (Reiteration from DP)

*   **Overlapping Subproblems:** Solutions to subproblems are reused.
*   **Optimal Substructure:** Optimal solution to the problem can be built from optimal solutions to its subproblems.

## Identifying 2D DP Problems

*   The state requires two (or sometimes more, leading to multi-dimensional DP) parameters to be uniquely defined.
*   Often involve:
    *   Two sequences/strings (e.g., Longest Common Subsequence, Edit Distance).
    *   A grid or matrix (e.g., Unique Paths, Minimum Path Sum).
    *   Problems on ranges `[i, j]` of a single sequence (e.g., Matrix Chain Multiplication, Longest Palindromic Substring).
*   The recurrence relation for `dp[i][j]` will typically depend on values like `dp[i-1][j]`, `dp[i][j-1]`, `dp[i-1][j-1]`, or values from sub-ranges.

## Common 2D DP Patterns and Problems

1.  **Grid Traversal:**
    *   `dp[i][j]` often represents the number of ways to reach cell `(i,j)` or the min/max cost/path to reach `(i,j)`.
    *   **Unique Paths:** `dp[i][j] = dp[i-1][j] + dp[i][j-1]`
    *   **Minimum Path Sum:** `dp[i][j] = grid[i][j] + min(dp[i-1][j], dp[i][j-1])`
    *   Problems: Maximal Square, Dungeon Game.

2.  **String/Sequence Comparison:**
    *   `dp[i][j]` often represents a property related to `string1[0...i-1]` and `string2[0...j-1]`.
    *   **Longest Common Subsequence (LCS):**
        If `s1[i-1] == s2[j-1]`: `dp[i][j] = 1 + dp[i-1][j-1]`
        Else: `dp[i][j] = max(dp[i-1][j], dp[i][j-1])`
    *   **Edit Distance (Levenshtein Distance):**
        If `s1[i-1] == s2[j-1]`: `dp[i][j] = dp[i-1][j-1]`
        Else: `dp[i][j] = 1 + min(dp[i-1][j],        // Deletion
                                 dp[i][j-1],        // Insertion
                                 dp[i-1][j-1])     // Replacement`
    *   Problems: Longest Palindromic Subsequence, Regular Expression Matching, Interleaving String.

3.  **Knapsack Type Problems (0/1 Knapsack):**
    *   `dp[i][w]` = maximum value using first `i` items with weight capacity `w`.
    *   If item `i` (with weight `wt[i-1]`, value `val[i-1]`) is included: `val[i-1] + dp[i-1][w - wt[i-1]]`
    *   If item `i` is excluded: `dp[i-1][w]`
    *   `dp[i][w] = max(val[i-1] + dp[i-1][w - wt[i-1]], dp[i-1][w])`
    *   Problems: Partition Equal Subset Sum, Target Sum.

4.  **Range DP / Interval DP:**
    *   `dp[i][j]` represents the solution for the sub-array or sub-string from index `i` to `j`.
    *   The recurrence often involves iterating a split point `k` between `i` and `j`: `dp[i][j] = operation(dp[i][k], dp[k+1][j], cost_of_combining)`
    *   **Matrix Chain Multiplication:** Find the most efficient way to multiply a chain of matrices.
    *   **Longest Palindromic Substring:** `dp[i][j]` is true if `s[i...j]` is a palindrome.
    *   Problems: Burst Balloons, Minimum Cost to Merge Stones.

## Steps to Solve a 2D DP Problem

1.  **Define the State:** What does `dp[i][j]` represent? Be precise.
2.  **Identify the Base Cases:** Smallest subproblems (e.g., `dp[0][0]`, `dp[i][0]`, `dp[0][j]`, or `dp[i][i]` for range DP).
3.  **Find the Recurrence Relation (Transition):** How does `dp[i][j]` relate to previously computed states? This is the core logic.
4.  **Determine the Order of Computation (for Tabulation):** How should the `dp` table be filled? Often row by row, column by column, or by increasing length of sub-array for range DP.
5.  **Implement (Memoization or Tabulation):**
    *   **Memoization (Top-Down):** Define a recursive function `solve(i, j)` that returns `dp[i][j]`.
    *   **Tabulation (Bottom-Up):** Use nested loops to fill the `dp` table.
6.  **Space Optimization (Optional):** If `dp[i][j]` only depends on the previous row (`dp[i-1]`) and/or current row values, space can sometimes be reduced from O(N*M) to O(M) or O(N).

## Implementations

*   [Python](./Implementations/Python/)
*   [Java](./Implementations/Java/)
*   [C++](./Implementations/Cpp/)
*   [JavaScript](./Implementations/JavaScript/)

*(Contributors: Please add examples of classic 2D DP problems.)*

## Further Reading & Resources

*   [Link to external article/video 1 on 2D DP Introduction]
*   [Link to external article/video 2 on Common 2D DP Patterns (LCS, Knapsack, Grid)]
