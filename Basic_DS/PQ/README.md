# Priority Queues (PQ)

## Overview

A priority queue is an abstract data type similar to a regular queue or stack data structure, but where additionally each element has a "priority" associated with it. In a priority queue, an element with high priority is served before an element with low priority. If two elements have the same priority, they are served according to their order in the queue (FIFO).

While often grouped with basic data structures, priority queues are typically implemented using more complex structures like Heaps.

## Key Concepts

*   **Priority-Based Ordering:** Elements are dequeued based on their priority, not just their arrival time.
*   **Core Operations:**
    *   `insert(element, priority)` or `add(element, priority)`: Adds an element with its associated priority.
    *   `extractMax()` or `pollMax()`: Removes and returns the element with the highest priority.
    *   `extractMin()` or `pollMin()`: Removes and returns the element with the lowest priority (depending on whether it's a max-priority queue or min-priority queue).
    *   `peekMax()` or `peekMin()`: Returns the highest/lowest priority element without removing it.
    *   `isEmpty()`: Checks if the priority queue is empty.
    *   `size()`: Returns the number of elements.
    *   `changePriority(element, newPriority)`: (Optional) Changes the priority of an existing element.
*   **Underlying Implementation:** Most commonly implemented using a **Heap** (Binary Heap). Can also be implemented using unsorted arrays/lists or sorted arrays/lists, but heaps offer better average time complexity for core operations.

## Time and Space Complexity (Using a Binary Heap)

| Operation        | Time Complexity (Avg & Worst) | Space Complexity |
|------------------|-------------------------------|------------------|
| Insert (Add)     | O(log n)                      | O(n)             |
| Extract-Min/Max  | O(log n)                      |                  |
| Peek-Min/Max     | O(1)                          |                  |
| Delete (any)     | O(log n) (if element position known) |                  |
| Change Priority  | O(log n) (if element position known) |                  |
| Build PQ from N elements | O(n)                   |                  |

## Implementations

*   **Using Heaps (most common):**
    *   [Python (`heapq` module for min-heap)](./Implementations/Python/)
    *   [Java (`PriorityQueue` class for min-heap by default)](./Implementations/Java/)
    *   [C++ (`std::priority_queue` for max-heap by default)](./Implementations/Cpp/)
    *   [JavaScript (custom heap implementation or library)](./Implementations/JavaScript/)

*(Contributors: Please add implementations, especially custom heap-based PQs or examples using built-in structures, in the respective language folders.)*

## Common Applications & Problems

*   **Dijkstra's Algorithm:** For finding the shortest path in a graph.
*   **Prim's Algorithm:** For finding a Minimum Spanning Tree (MST) in a graph.
*   **Huffman Coding:** For data compression.
*   **Event-driven simulation:** Managing events by their time.
*   **Task Scheduling:** Operating systems scheduling tasks based on priority.
*   Kth Largest/Smallest Element in an Array/Stream
*   Merge K Sorted Lists
*   Top K Frequent Elements
*   Find Median from Data Stream
*   ... (add more problems)

*(Contributors: Please add links to problem statements and solutions.)*

## Further Reading & Resources

*   [Link to external article/video 1 on Heaps]
*   [Link to external article/video 2 on Priority Queues]
