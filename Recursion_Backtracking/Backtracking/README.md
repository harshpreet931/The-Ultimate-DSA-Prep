# Backtracking

## Overview

Backtracking is an algorithmic technique for solving problems recursively by trying to build a solution incrementally, one piece at a time, removing those solutions that fail to satisfy the constraints of the problem at any point in time (by "backtracking").

It is a refined brute-force approach that systematically searches for a solution. If a partial solution cannot be extended to a complete solution, the algorithm backtracks by undoing the last choice and trying an alternative.

## Core Idea

1.  **Choose:** Make a choice at the current decision point.
2.  **Explore:** Recursively explore the consequences of that choice.
3.  **Unchoose (Backtrack):** If the exploration does not lead to a solution (or all solutions from this path have been found), undo the choice and try another available option at the current decision point.

This process creates a "state-space tree" where nodes represent partial solutions, and edges represent choices. Backtracking is essentially a form of Depth-First Search (DFS) on this state-space tree.

## General Algorithm Template

```
function backtrack(current_state, other_parameters):
    // 1. Base Case(s): Check if a solution is found or if the path is invalid
    if (is_solution(current_state)):
        add current_state to solutions
        return
    if (is_invalid(current_state) or cannot_extend(current_state)):
        return

    // 2. Iterate through all possible choices/moves
    for each choice in get_possible_choices(current_state):
        // a. Make the choice
        apply_choice(current_state, choice)

        // b. Explore: Recurse
        backtrack(current_state, other_parameters)

        // c. Unchoose (Backtrack): Revert the choice
        undo_choice(current_state, choice)
```

## Key Characteristics

*   **Problem Type:** Often used for constraint satisfaction problems (CSPs), pathfinding, and generating all possible configurations (e.g., permutations, combinations, subsets).
*   **State Space:** Explores a tree of possibilities.
*   **Pruning:** The "backtracking" step prunes branches of the state-space tree that cannot lead to a valid solution, making it more efficient than naive brute-force.
*   **Recursive Nature:** Typically implemented using recursion.

## When to Use Backtracking

Consider backtracking when you need to:
*   Find all possible solutions.
*   Find one solution that satisfies certain constraints.
*   Find an optimal solution among all possibilities (though this might blend with dynamic programming or branch and bound).

The problem usually involves a sequence of choices, and the validity of a choice depends on previous choices.

## Common Problems Solved with Backtracking

*   **N-Queens Problem:** Place N queens on an N×N chessboard so that no two queens threaten each other.
*   **Sudoku Solver:** Fill a 9×9 grid so that each column, each row, and each of the nine 3×3 subgrids contain all digits from 1 to 9.
*   **Generating Permutations:** Find all possible orderings of a set of items.
*   **Generating Combinations:** Find all possible subsets of a certain size.
*   **Subsets (Power Set):** Find all possible subsets of a set.
*   **Word Search Puzzles:** Finding words in a grid of letters.
*   **Pathfinding in a Maze:** Finding a path from a start to an end point.
*   **Graph Coloring Problem:** Assign colors to vertices of a graph such that no two adjacent vertices share the same color.
*   **Combination Sum**
*   **Letter Combinations of a Phone Number**
*   **Palindrome Partitioning**

## Advantages

*   Can solve complex problems that are hard to tackle with other direct methods.
*   Relatively simple to implement once the recursive structure is understood.
*   Guaranteed to find a solution if one exists (for finite search spaces).

## Disadvantages

*   Can be slow (exponential time complexity in the worst case) if the search space is very large and pruning is not effective.
*   The "state" can sometimes be complex to manage (e.g., copying vs. modifying in place and reverting).
*   Stack overflow can be an issue for deep recursion if not managed.

## Implementations

*   [Python](./Implementations/Python/)
*   [Java](./Implementations/Java/)
*   [C++](./Implementations/Cpp/)
*   [JavaScript](./Implementations/JavaScript/)

*(Contributors: Please add examples of classic backtracking problems.)*

## Further Reading & Resources

*   [Link to external article/video 1 on Backtracking basics]
*   [Link to external article/video 2 with examples like N-Queens or Sudoku]
