# Stacks

## Overview

A stack is an abstract data type that serves as a collection of elements, with two main principal operations:
*   **Push:** Adds an element to the collection.
*   **Pop:** Removes the most recently added element that was not yet removed.
The order in which elements come off a stack gives rise to its alternative name, LIFO (last in, first out).

## Key Concepts

*   **LIFO Principle:** Last In, First Out.
*   **Core Operations:**
    *   `push(element)`: Add an element to the top of the stack.
    *   `pop()`: Remove and return the top element of the stack.
    *   `peek()` or `top()`: Return the top element without removing it.
    *   `isEmpty()`: Check if the stack is empty.
    *   `size()`: Return the number of elements in the stack.
*   **Underlying Implementation:** Can be implemented using arrays/dynamic arrays or linked lists.
*   **Stack Overflow/Underflow:** Conditions where push is attempted on a full stack, or pop/peek on an empty stack.

## Time and Space Complexity (for common implementations)

| Operation | Array Implementation (Avg) | Linked List Implementation (Avg) | Space Complexity |
|-----------|----------------------------|------------------------------------|------------------|
| Push      | O(1) (amortized for dynamic array) | O(1)                             | O(n)             |
| Pop       | O(1)                       | O(1)                             |                  |
| Peek/Top  | O(1)                       | O(1)                             |                  |
| isEmpty   | O(1)                       | O(1)                             |                  |
| Size      | O(1)                       | O(1) (if size tracked)           |                  |

## Implementations

*   [Python](./Implementations/Python/)
*   [Java](./Implementations/Java/)
*   [C++](./Implementations/Cpp/)
*   [JavaScript](./Implementations/JavaScript/)

*(Contributors: Please add implementations in the respective language folders.)*

## Common Applications & Problems

*   Function call management (call stack)
*   Expression evaluation (e.g., infix to postfix, postfix evaluation)
*   Undo/redo functionality in software
*   Backtracking algorithms (e.g., maze solving, N-Queens)
*   Valid Parentheses
*   Min Stack (design a stack that supports push, pop, top, and retrieving the minimum element in constant time)
*   Implement Queue using Stacks
*   Daily Temperatures
*   ... (add more problems)

*(Contributors: Please add links to problem statements and solutions.)*

## Further Reading & Resources

*   [Link to external article/video 1]
*   [Link to external article/video 2]
