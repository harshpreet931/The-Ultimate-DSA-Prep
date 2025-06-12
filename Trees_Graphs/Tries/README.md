# Tries (Prefix Trees)

## Overview

A Trie, also known as a prefix tree or digital tree, is a type of k-ary search tree used for locating specific keys from within a set. These keys are most often strings, with links between nodes defined not by the whole key, but by individual characters. In order to access a key (to recover its value, change it, or remove it), the trie is traversed depth-first, following the links corresponding to each character in the key.

## Key Concepts

*   **Node Structure:**
    *   An array/map of pointers to child nodes (one for each possible character in the alphabet, e.g., 26 for lowercase English letters).
    *   A boolean flag `isEndOfWord` (or similar) to mark if a node represents the end of a complete word.
    *   Optionally, a value associated with the word if the trie is used as a map.
*   **Root Node:** Represents an empty prefix.
*   **Path from Root:** A path from the root to a node marked as `isEndOfWord` represents a complete word stored in the trie.
*   **Prefix Searching:** Efficiently search for words with a given prefix. All words sharing that prefix will reside in the subtree rooted at the node corresponding to the end of that prefix.

## Operations

*   **Insertion:**
    1.  Start from the root.
    2.  For each character in the word, traverse to the corresponding child node.
    3.  If a child node for a character does not exist, create it.
    4.  Move to the child node.
    5.  After processing all characters, mark the current node's `isEndOfWord` as true.
*   **Search (for a complete word):**
    1.  Start from the root.
    2.  For each character in the word, traverse to the corresponding child node.
    3.  If at any point a child node for a character does not exist, the word is not in the trie.
    4.  After processing all characters, if the current node's `isEndOfWord` is true, the word exists.
*   **Search (for a prefix / startsWith):**
    1.  Similar to word search, but after processing all characters of the prefix, if the traversal was successful to a node (regardless of `isEndOfWord`), the prefix exists.
*   **Deletion:**
    1.  Search for the word. If not found, do nothing.
    2.  If found, unmark `isEndOfWord` at the final node.
    3.  (Optional but recommended for space efficiency) If the final node has no other children and is not an end of another word, it can be removed. This process can be recursively applied upwards to its parent.

## Time and Space Complexity

Let `L` be the length of the key (word/prefix) and `N` be the number of keys stored in the trie. Let `A` be the alphabet size.

| Operation | Time Complexity | Space Complexity (Worst Case) |
|-----------|-----------------|-------------------------------|
| Insertion | O(L)            | O(N * L * A) (naive, if each node stores full alphabet array) or O(N * L) (if nodes only store actual children links, e.g. using hash maps) |
| Search    | O(L)            |                               |
| Deletion  | O(L)            |                               |
| StartsWith (Prefix Search) | O(L) |                           |

*Space complexity can be high if the alphabet is large and nodes are implemented with fixed-size arrays for children. Using hash maps for children can optimize space for sparse tries but might slightly increase constant factors for time.*

## Implementations

*   [Python](./Implementations/Python/)
*   [Java](./Implementations/Java/)
*   [C++](./Implementations/Cpp/)
*   [JavaScript](./Implementations/JavaScript/)

*(Contributors: Please add implementations in the respective language folders.)*

## Common Applications & Problems

*   Autocomplete / Typeahead suggestions
*   Spell checkers
*   IP routing (longest prefix match)
*   Dictionary implementations
*   Bioinformatics (e.g., storing DNA sequences)
*   Implement Trie (Prefix Tree)
*   Word Search II (on a 2D board)
*   Design Add and Search Words Data Structure
*   Maximum XOR of Two Numbers in an Array (using a binary trie)
*   ... (add more problems)

## Advantages

*   Very fast prefix-based searches (O(L)).
*   Efficient for scenarios with many words sharing common prefixes.
*   Can be faster than hash tables for some use cases (e.g., if hash collisions are frequent or string hashing is slow).
*   Naturally sorts words in lexicographical order if traversed appropriately.

## Disadvantages

*   Can consume a lot of memory, especially if keys are long or the alphabet is large and child pointers are stored in arrays.
*   Not as space-efficient as hash tables for storing a small number of very long, distinct strings.

## Further Reading & Resources

*   [Link to external article/video 1]
*   [Link to external article/video 2]
