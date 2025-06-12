# Binary Trees

## Overview

A binary tree is a tree data structure in which each node has at most two children, which are referred to as the *left child* and the *right child*. A recursive definition using just set theory notions is that a (non-empty) binary tree is a tuple (L, S, R), where L and R are binary trees or empty sets and S is a singleton set containing the root.

## Key Concepts

*   **Node Structure:** Contains data, a pointer to the left child, and a pointer to the right child.
*   **Root:** The topmost node in the tree.
*   **Parent, Child, Sibling:** Standard familial relationships between nodes.
*   **Leaf Node:** A node with no children.
*   **Internal Node:** A node with at least one child.
*   **Depth of a Node:** The number of edges from the root to the node.
*   **Height of a Tree:** The number of edges on the longest path from the root to a leaf.
*   **Full Binary Tree:** Every node has 0 or 2 children.
*   **Complete Binary Tree:** All levels are completely filled except possibly the last level, which is filled from left to right.
*   **Perfect Binary Tree:** All internal nodes have two children and all leaf nodes are at the same level.
*   **Balanced Binary Tree:** The heights of the two child subtrees of any node differ by at most one (e.g., AVL, Red-Black trees). This is a stricter definition often associated with self-balancing BSTs. For general binary trees, "balanced" can be a looser term.

## Tree Traversals

*   **In-order Traversal (Left, Root, Right):** Visits nodes in ascending order in a BST.
*   **Pre-order Traversal (Root, Left, Right):** Useful for creating a copy of the tree.
*   **Post-order Traversal (Left, Right, Root):** Useful for deleting nodes in a tree.
*   **Level-order Traversal (Breadth-First Search - BFS):** Visits nodes level by level.

## Time and Space Complexity (for N nodes)

| Operation          | Time Complexity (Avg) | Time Complexity (Worst) | Space Complexity (for traversals) |
|--------------------|-----------------------|-------------------------|-----------------------------------|
| Search             | O(N)                  | O(N)                    | O(H) or O(N) for recursive, O(N) for iterative BFS |
| Insertion          | O(H) or O(N)\*        | O(H) or O(N)\*          |                                   |
| Deletion           | O(H) or O(N)\*        | O(H) or O(N)\*          |                                   |
| In-order Traversal | O(N)                  | O(N)                    | O(H) (recursive), O(N) (iterative) |
| Pre-order Traversal| O(N)                  | O(N)                    | O(H) (recursive), O(N) (iterative) |
| Post-order Traversal| O(N)                 | O(N)                    | O(H) (recursive), O(N) (iterative) |
| Level-order Traversal| O(N)                | O(N)                    | O(W) (max width, can be O(N))     |

*H is the height of the tree. For a skewed tree, H can be N. For a balanced tree, H is O(log N).*
*\*Insertion/Deletion in a general binary tree depends on where you insert/delete. If it's a specific structure like a BST, complexities are more defined.*

## Implementations

*   [Python](./Implementations/Python/)
*   [Java](./Implementations/Java/)
*   [C++](./Implementations/Cpp/)
*   [JavaScript](./Implementations/JavaScript/)

*(Contributors: Please add implementations in the respective language folders.)*

## Common Problems

*   Maximum Depth of Binary Tree
*   Same Tree (check if two trees are identical)
*   Invert Binary Tree
*   Binary Tree Level Order Traversal
*   Binary Tree Right Side View
*   Lowest Common Ancestor (LCA) of a Binary Tree
*   Construct Binary Tree from Preorder and Inorder Traversal
*   Validate Binary Search Tree (though this is specific to BSTs, often asked in BT context)
*   Path Sum
*   Diameter of Binary Tree
*   ... (add more problems)

*(Contributors: Please add links to problem statements and solutions.)*

## Further Reading & Resources

*   [Link to external article/video 1]
*   [Link to external article/video 2]
