# Queues

## Overview

A queue is an abstract data type that serves as a collection of elements, with two main principal operations:
*   **Enqueue (or Add):** Adds an element to the rear of the collection.
*   **Dequeue (or Remove):** Removes the element from the front of the collection.
The order in which elements come off a queue gives rise to its alternative name, FIFO (first in, first out).

## Key Concepts

*   **FIFO Principle:** First In, First Out.
*   **Core Operations:**
    *   `enqueue(element)` or `add(element)`: Add an element to the rear of the queue.
    *   `dequeue()` or `remove()`: Remove and return the front element of the queue.
    *   `peek()` or `front()`: Return the front element without removing it.
    *   `isEmpty()`: Check if the queue is empty.
    *   `size()`: Return the number of elements in the queue.
*   **Underlying Implementation:** Can be implemented using arrays (often circular arrays/buffers) or linked lists.
*   **Queue Full/Empty Conditions:** Considerations for fixed-size array implementations.

## Time and Space Complexity (for common implementations)

| Operation      | Array (Circular) Implementation (Avg) | Linked List Implementation (Avg) | Space Complexity |
|----------------|---------------------------------------|------------------------------------|------------------|
| Enqueue (Add)  | O(1) (amortized for dynamic array)    | O(1) (if tail pointer maintained)  | O(n)             |
| Dequeue (Remove)| O(1)                                  | O(1)                             |                  |
| Peek/Front     | O(1)                                  | O(1)                             |                  |
| isEmpty        | O(1)                                  | O(1)                             |                  |
| Size           | O(1)                                  | O(1) (if size tracked)           |                  |

## Types of Queues

*   **Simple Queue:** Standard FIFO queue.
*   **Circular Queue:** Array-based queue where the last position is connected back to the first to make a circle. Efficiently uses array space.
*   **Priority Queue:** Each element has a priority, and elements with higher priority are dequeued before elements with lower priority. (Often a separate data structure, but related).
*   **Double-Ended Queue (Deque):** Elements can be added or removed from either the front or the rear.

## Implementations

*   [Python](./Implementations/Python/)
*   [Java](./Implementations/Java/)
*   [C++](./Implementations/Cpp/)
*   [JavaScript](./Implementations/JavaScript/)

*(Contributors: Please add implementations in the respective language folders.)*

## Common Applications & Problems

*   Resource sharing (e.g., CPU scheduling, printer queues)
*   Breadth-First Search (BFS) in graphs and trees
*   Buffering data (e.g., in streaming)
*   Task scheduling
*   Implement Stack using Queues
*   Sliding Window Maximum
*   Number of Recent Calls
*   ... (add more problems)

*(Contributors: Please add links to problem statements and solutions.)*

## Further Reading & Resources

*   [Link to external article/video 1]
*   [Link to external article/video 2]
