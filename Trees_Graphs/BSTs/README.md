# Binary Search Trees (BSTs)

## Overview

A Binary Search Tree (BST) is a node-based binary tree data structure which has the following properties:
*   The left subtree of a node contains only nodes with keys lesser than the node's key.
*   The right subtree of a node contains only nodes with keys greater than the node's key.
*   The left and right subtree each must also be a binary search tree.
*   There must be no duplicate nodes (though variations can allow duplicates).

These properties allow for efficient searching, insertion, and deletion operations.

## Key Concepts

*   **BST Property:** Left child < Parent < Right child.
*   **Search:** Start from the root, if the key is less than the current node, go left; if greater, go right. Repeat until the key is found or a null pointer is reached.
*   **Insertion:** Search for the key. If found, handle duplicates (e.g., ignore, store count, or allow). If not found, insert at the last null spot encountered during the search, maintaining BST property.
*   **Deletion:**
    *   **Node with no children (leaf):** Simply remove the node.
    *   **Node with one child:** Replace the node with its child.
    *   **Node with two children:** Find its in-order successor (smallest node in the right subtree) or in-order predecessor (largest node in the left subtree). Copy the successor's/predecessor's content to the node and delete the successor/predecessor.
*   **In-order Traversal:** Yields nodes in sorted (ascending) order.
*   **Balanced vs. Unbalanced BSTs:**
    *   Performance degrades to O(n) for operations if the tree becomes skewed (e.g., inserting sorted data).
    *   **Self-Balancing BSTs** (e.g., AVL Trees, Red-Black Trees) automatically adjust the tree structure to maintain balance (height of O(log n)).

## Time and Space Complexity (for N nodes)

| Operation        | Time Complexity (Avg - Balanced) | Time Complexity (Worst - Skewed) | Space Complexity |
|------------------|---------------------------------|----------------------------------|------------------|
| Search           | O(log N)                        | O(N)                             | O(H) for recursion |
| Insertion        | O(log N)                        | O(N)                             | O(H) for recursion |
| Deletion         | O(log N)                        | O(N)                             | O(H) for recursion |
| Min/Max Element  | O(log N)                        | O(N)                             | O(H) for recursion |
| In-order Successor/Predecessor | O(log N)          | O(N)                             | O(H) for recursion |

*H is the height of the tree. For a balanced BST, H = O(log N). For a skewed BST, H = O(N).*

## Implementations

*   [Python](./Implementations/Python/)
*   [Java](./Implementations/Java/)
*   [C++](./Implementations/Cpp/)
*   [JavaScript](./Implementations/JavaScript/)

*(Contributors: Please add implementations, including self-balancing variants if possible, in the respective language folders.)*

## Common Problems

*   Validate Binary Search Tree
*   Lowest Common Ancestor (LCA) of a BST
*   Convert Sorted Array to Binary Search Tree
*   Kth Smallest Element in a BST
*   Inorder Successor in BST
*   Delete Node in a BST
*   Range Sum of BST
*   Balance a Binary Search Tree
*   ... (add more problems)

## Advantages

*   Efficient search, insert, delete operations on average (O(log N) for balanced trees).
*   In-order traversal yields sorted data.
*   Can be used to implement dynamic sets and lookup tables.

## Disadvantages

*   Performance degrades significantly if the tree becomes unbalanced.
*   More complex to implement than simple arrays or linked lists, especially self-balancing versions.

## Further Reading & Resources

*   [Link to external article/video 1 on BST basics]
*   [Link to external article/video 2 on Self-Balancing BSTs (e.g., AVL, Red-Black)]
