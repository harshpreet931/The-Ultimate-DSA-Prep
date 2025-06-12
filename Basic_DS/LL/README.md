# Linked Lists (LL)

## Overview

A linked list is a linear collection of data elements whose order is not given by their physical placement in memory. Instead, each element points to the next. It is a data structure consisting of a collection of nodes which together represent a sequence. In its most basic form, each node contains: data, and a reference (in other words, a link) to the next node in the sequence.

## Key Concepts

*   **Node Structure:** Data and Pointer(s) to next (and previous for Doubly LL).
*   **Types of Linked Lists:**
    *   Singly Linked List
    *   Doubly Linked List
    *   Circular Linked List
*   **Head and Tail Pointers:** Marking the beginning and end of the list.
*   **Traversal:** Iterating through the list.
*   **Common Operations:**
    *   Insertion (at beginning, end, specific position)
    *   Deletion (at beginning, end, specific position/value)
    *   Search (for a value)
    *   Update (a node's value)
*   **Advantages:** Dynamic size, ease of insertion/deletion.
*   **Disadvantages:** No random access (O(n) to access an element), extra memory for pointers.

## Time and Space Complexity

| Operation             | Singly LL (Avg) | Doubly LL (Avg) | Space Complexity |
|-----------------------|-----------------|-----------------|------------------|
| Access (by index/val) | O(n)            | O(n)            | O(n)             |
| Search (by value)     | O(n)            | O(n)            |                  |
| Insertion (at head)   | O(1)            | O(1)            |                  |
| Insertion (at tail)   | O(n) / O(1)\*   | O(1)\*          |                  |
| Insertion (middle)    | O(n)            | O(n)            |                  |
| Deletion (at head)    | O(1)            | O(1)            |                  |
| Deletion (at tail)    | O(n)            | O(1)\*          |                  |
| Deletion (middle)     | O(n)            | O(n)            |                  |

\* O(1) if a tail pointer is maintained.

## Implementations

*   [Python](./Implementations/Python/)
*   [Java](./Implementations/Java/)
*   [C++](./Implementations/Cpp/)
*   [JavaScript](./Implementations/JavaScript/)

*(Contributors: Please add implementations in the respective language folders.)*

## Common Problems

*   Reverse a Linked List
*   Detect Cycle in a Linked List
*   Merge Two Sorted Lists
*   Remove Nth Node From End of List
*   Intersection of Two Linked Lists
*   Palindrome Linked List
*   Add Two Numbers (represented by LL)
*   ... (add more problems)

*(Contributors: Please add links to problem statements and solutions.)*

## Further Reading & Resources

*   [Link to external article/video 1]
*   [Link to external article/video 2]
