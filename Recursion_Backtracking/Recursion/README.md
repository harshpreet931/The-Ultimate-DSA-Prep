# Recursion

## Overview

Recursion is a programming technique where a function calls itself directly or indirectly to solve a problem. It breaks down a problem into smaller, self-similar subproblems until a **base case** is reached, which can be solved directly. The solutions to the subproblems are then combined to solve the original problem.

## Key Concepts

*   **Base Case(s):**
    *   The simplest instance(s) of the problem that can be solved directly without further recursion.
    *   Essential to prevent infinite recursion. A recursive function must always have at least one base case.
*   **Recursive Step (Recursive Call):**
    *   The part of the function where it calls itself with modified input, moving closer to the base case.
    *   The problem is broken down into smaller or simpler versions of itself.
*   **Call Stack:**
    *   Each recursive call adds a new frame to the call stack, storing its local variables and parameters.
    *   When a base case is reached, the function returns, and its frame is popped from the stack.
    *   Excessive recursion depth can lead to a **stack overflow error**.
*   **Divide and Conquer:** Many recursive algorithms follow this paradigm:
    1.  **Divide:** Break the problem into smaller subproblems.
    2.  **Conquer:** Solve the subproblems recursively.
    3.  **Combine:** Combine the solutions of subproblems to get the solution for the original problem.

## Structure of a Recursive Function

```
function recursiveFunction(parameters):
    // 1. Base Case(s)
    if (condition for base case is met):
        return (some simple value or action)

    // 2. Recursive Step
    // Modify parameters to move towards the base case
    modified_parameters = ...
    result_from_subproblem = recursiveFunction(modified_parameters)

    // 3. Combine (if necessary)
    // Process result_from_subproblem to form the current solution
    current_solution = ...
    return current_solution
```

## Types of Recursion

*   **Direct Recursion:** A function calls itself directly.
*   **Indirect Recursion:** A function calls another function, which eventually calls the original function (e.g., A calls B, B calls A).
*   **Tail Recursion:** The recursive call is the very last operation in the function. Tail-recursive functions can often be optimized by compilers into iterative code (Tail Call Optimization - TCO), avoiding stack overflow.
*   **Head Recursion:** The recursive call is the first operation.
*   **Tree Recursion:** A function makes more than one recursive call (e.g., Fibonacci sequence, tree traversals).
*   **Linear Recursion:** A function makes at most one recursive call.

## Advantages of Recursion

*   **Elegance and Readability:** Can lead to simpler, more intuitive solutions for problems that are naturally recursive (e.g., tree traversals, factorial, Fibonacci).
*   **Problem Decomposition:** Naturally fits divide-and-conquer strategies.
*   **Handling Complex Data Structures:** Well-suited for operations on recursive data structures like trees and linked lists.

## Disadvantages of Recursion

*   **Performance Overhead:** Function calls can be slower than iteration due to stack frame management.
*   **Stack Overflow:** Deep recursion can exhaust the call stack memory.
*   **Debugging Complexity:** Tracing recursive calls can be more challenging.
*   **Not Always Intuitive:** For some, iterative solutions might be easier to understand initially.

## Recursion vs. Iteration

*   Every recursive algorithm can be implemented iteratively (often using an explicit stack).
*   Every iterative algorithm can be implemented recursively (though it might not always be natural).
*   Choice depends on the problem, readability, performance considerations, and potential for stack overflow.

## Common Problems Solved with Recursion

*   Factorial of a number
*   Fibonacci sequence
*   Tree traversals (In-order, Pre-order, Post-order)
*   Graph traversals (DFS)
*   Merge Sort, Quick Sort
*   Towers of Hanoi
*   Binary Search (recursive version)
*   Generating permutations and combinations
*   Many backtracking problems (see Backtracking section)
*   ... (add more problems)

## Implementations

*   [Python](./Implementations/Python/)
*   [Java](./Implementations/Java/)
*   [C++](./Implementations/Cpp/)
*   [JavaScript](./Implementations/JavaScript/)

*(Contributors: Please add examples of various recursive functions and patterns.)*

## Further Reading & Resources

*   [Link to external article/video 1 on Recursion basics]
*   [Link to external article/video 2 on Recursion vs Iteration]
*   [Link to external article/video 3 on Tail Call Optimization]
