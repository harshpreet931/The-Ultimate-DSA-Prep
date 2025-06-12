# Greedy Algorithms

## Overview

A greedy algorithm is an algorithmic paradigm that builds up a solution piece by piece, always choosing the next piece that offers the most obvious and immediate benefit (i.e., making a locally optimal choice) in the hope of finding a global optimum.

Greedy algorithms do not always yield a globally optimal solution, but for many problems, they do. When they work, they are often simpler to implement and more efficient than other techniques like Dynamic Programming.

## Key Characteristics

1.  **Greedy Choice Property:** A global optimum can be arrived at by selecting a locally optimal choice (the greedy choice) at each step.
2.  **Optimal Substructure:** An optimal solution to the problem contains optimal solutions to its subproblems (similar to Dynamic Programming).

The critical part is proving that the greedy choice property holds for the problem at hand. If it doesn't, a greedy approach might lead to a suboptimal solution.

## General Approach

1.  **Identify a Greedy Choice:** Determine a criterion for making a locally optimal choice at each step. This often involves sorting the input or using a priority queue.
2.  **Make the Choice:** Select the element or action that satisfies the greedy criterion.
3.  **Reduce the Problem:** The choice made reduces the problem to a smaller subproblem.
4.  **Repeat:** Continue making greedy choices until the problem is solved.
5.  **Prove Correctness (Important!):**
    *   **Greedy choice property:** Show that any optimal solution can be transformed into the greedy solution without worsening its quality.
    *   **Optimal substructure:** Show that after making the greedy choice, the remaining subproblem, if solved optimally, leads to an overall optimal solution.
    *   Often done by an "exchange argument" or "greedy stays ahead" proof.

## When to Use Greedy Algorithms

*   When the problem has the greedy choice property and optimal substructure.
*   When you need a relatively simple and efficient algorithm, and an approximate solution is acceptable if the greedy choice doesn't guarantee optimality (though for classic greedy problems, it does).
*   Often involves selection, scheduling, or finding minimum/maximum values under certain constraints.

## Greedy vs. Dynamic Programming

| Feature          | Greedy                                       | Dynamic Programming                             |
|------------------|----------------------------------------------|-------------------------------------------------|
| **Choices**      | Makes one locally optimal choice at each step. | Explores multiple choices at each step.         |
| **Subproblems**  | Only one subproblem results from each choice. | May solve many overlapping subproblems.         |
| **Proof**        | Relies on proving the greedy choice property. | Relies on optimal substructure and overlapping subproblems. |
| **Optimality**   | May not always be globally optimal (unless proven). | Generally finds the global optimum.             |
| **Implementation**| Often simpler, iterative.                    | Can be recursive (memoization) or iterative (tabulation). |

Sometimes, a problem might seem greedy, but a DP solution is required because a local optimum doesn't guarantee a global one (e.g., 0/1 Knapsack is DP, Fractional Knapsack is Greedy).

## Common Problems Solved with Greedy Algorithms

*   **Activity Selection Problem:** Select the maximum number of non-overlapping activities from a set of activities, each with a start and finish time. (Greedy choice: select the activity that finishes earliest).
*   **Fractional Knapsack Problem:** Maximize the value of items in a knapsack where fractions of items can be taken. (Greedy choice: select items with the highest value-to-weight ratio).
*   **Huffman Coding:** For data compression. (Greedy choice: merge two trees with the smallest frequencies).
*   **Prim's Algorithm for MST:** (Greedy choice: add the minimum weight edge connecting a vertex in the current MST to one outside).
*   **Kruskal's Algorithm for MST:** (Greedy choice: add the minimum weight edge that doesn't form a cycle).
*   **Dijkstra's Algorithm for Shortest Path:** (Greedy choice: select the unvisited vertex with the smallest known distance from the source).
*   **Coin Change (making change with fewest coins, if canonical coin system):** (Greedy choice: use the largest denomination coin less than or equal to the remaining amount). *Note: This doesn't work for all coin systems.*
*   Task Scheduler (LeetCode)
*   Jump Game (LeetCode)
*   Gas Station (LeetCode)
*   Merge Intervals (LeetCode, involves sorting which is a common greedy pre-step)

## Implementations

*   [Python](./Implementations/Python/)
*   [Java](./Implementations/Java/)
*   [C++](./Implementations/Cpp/)
*   [JavaScript](./Implementations/JavaScript/)

*(Contributors: Please add examples of classic greedy algorithms.)*

## Further Reading & Resources

*   [Link to external article/video 1 on Introduction to Greedy Algorithms]
*   [Link to external article/video 2 on Proving Greedy Algorithm Correctness]
*   [Link to external article/video 3 on Greedy vs. DP with examples]
