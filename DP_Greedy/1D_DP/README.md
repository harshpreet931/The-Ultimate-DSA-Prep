# 1D Dynamic Programming (1D DP)

## Overview

Dynamic Programming (DP) is an algorithmic technique for solving complex problems by breaking them down into simpler, overlapping subproblems and storing the results of these subproblems (usually in an array or hash map) to avoid redundant computations.

**1D Dynamic Programming** refers to DP problems where the state can be represented by a single parameter, often leading to solutions stored in a one-dimensional array.

## Key Concepts of Dynamic Programming

1.  **Overlapping Subproblems:** A problem has overlapping subproblems if it can be broken down into subproblems that are reused multiple times. DP stores the solutions to these subproblems.
    *   Example: In Fibonacci sequence `fib(n) = fib(n-1) + fib(n-2)`, `fib(n-2)` is computed multiple times if not memoized.
2.  **Optimal Substructure:** A problem exhibits optimal substructure if an optimal solution to the problem can be constructed from optimal solutions to its subproblems.
    *   Example: The shortest path to a destination contains shortest paths to intermediate nodes.

## Approaches to Dynamic Programming

1.  **Memoization (Top-Down):**
    *   Solve the problem recursively, but store the result of each subproblem encountered.
    *   If a subproblem is encountered again, return the stored result instead of recomputing.
    *   Uses a lookup table (e.g., array, hash map) for memoization.
    *   Intuitive, follows the natural recursive structure.

    ```python
    # Example: Fibonacci with Memoization
    memo = {}
    def fib_memo(n):
        if n in memo: return memo[n]
        if n <= 1: return n
        memo[n] = fib_memo(n-1) + fib_memo(n-2)
        return memo[n]
    ```

2.  **Tabulation (Bottom-Up):**
    *   Solve subproblems in a specific order, typically starting from the smallest/simplest ones.
    *   Store results in a table (e.g., a 1D array for 1D DP).
    *   Build up the solution to the original problem by using previously computed results.
    *   Often iterative, can avoid recursion overhead and stack overflow issues.

    ```python
    # Example: Fibonacci with Tabulation
    def fib_tab(n):
        if n <= 1: return n
        dp = [0] * (n + 1)
        dp[0] = 0
        dp[1] = 1
        for i in range(2, n + 1):
            dp[i] = dp[i-1] + dp[i-2]
        return dp[n]
    ```

## Identifying 1D DP Problems

*   The state of the problem at any point can be defined by a single variable (e.g., `dp[i]` depends on `dp[i-1]`, `dp[i-2]`, etc.).
*   Often involves sequences, arrays, or problems where you make decisions at each step `i` based on previous steps.
*   The goal is usually to find a maximum/minimum value, count possibilities, or determine feasibility.

## Common 1D DP Patterns and Problems

1.  **Fibonacci Sequence & Variations:**
    *   `dp[i] = dp[i-1] + dp[i-2]`
    *   Problems: Climbing Stairs, Tribonacci Number.
2.  **Maximum/Minimum Sum/Value Subsequence/Subarray (with constraints):**
    *   **House Robber:** `dp[i] = max(nums[i] + dp[i-2], dp[i-1])` (rob current house or not)
    *   **Maximum Subarray Sum (Kadane's Algorithm):** `dp[i] = max(nums[i], nums[i] + dp[i-1])`
    *   Problems: Best Time to Buy and Sell Stock (with variations).
3.  **Counting Problems:**
    *   **Coin Change (Number of ways):** `dp[amount] += dp[amount - coin]` (if considering permutations) or more complex if combinations. (Note: Coin Change for min coins is also common but can be 1D).
    *   **Decode Ways:** `dp[i]` depends on `dp[i-1]` and `dp[i-2]` based on valid decodings.
4.  **Decision Making (Boolean DP):**
    *   **Word Break:** `dp[i]` is true if `s[0...i-1]` can be segmented. `dp[i] = OR (dp[j] AND s[j...i-1] in wordDict)`.
    *   **Partition Equal Subset Sum:** (Can be 2D, but a 1D variation exists for checking if a sum is possible).

## Steps to Solve a DP Problem

1.  **Define the State:** What information do you need to store to solve subproblems? For 1D DP, this is often `dp[i]` representing the solution for the problem up to index `i` or for value `i`.
2.  **Identify the Base Cases:** What are the simplest subproblems you can solve directly? (e.g., `dp[0]`, `dp[1]`).
3.  **Find the Recurrence Relation (Transition):** How can you solve `dp[i]` using solutions to smaller subproblems (e.g., `dp[i-1]`, `dp[i-2]`)? This is the core logic.
4.  **Determine the Order of Computation (for Tabulation):** In what order should you fill your DP table? Usually from base cases upwards.
5.  **Implement (Memoization or Tabulation):**
6.  **Space Optimization (Optional):** If `dp[i]` only depends on a few previous states (e.g., `dp[i-1]`, `dp[i-2]`), you might be able to reduce space complexity from O(n) to O(1) by only storing those few states.

## Implementations

*   [Python](./Implementations/Python/)
*   [Java](./Implementations/Java/)
*   [C++](./Implementations/Cpp/)
*   [JavaScript](./Implementations/JavaScript/)

*(Contributors: Please add examples of classic 1D DP problems using both memoization and tabulation.)*

## Further Reading & Resources

*   [Link to external article/video 1 on Introduction to Dynamic Programming]
*   [Link to external article/video 2 on 1D DP patterns and examples]
