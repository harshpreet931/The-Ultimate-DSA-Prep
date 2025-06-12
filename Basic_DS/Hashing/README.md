# Hashing

## Overview

Hashing is a technique used to uniquely identify a specific object from a group of similar objects. In hashing, large keys are converted into small keys by using hash functions. The values are then stored in a data structure called a hash table. The main idea of a hash table is to use a hash function to map keys to bucket locations in an array.

## Key Concepts

*   **Hash Function:** A function that computes a numerical hash value (hash code) from an input key.
    *   Properties of a good hash function: deterministic, uniform distribution, fast computation, minimizes collisions.
*   **Hash Table (Hash Map):** A data structure that implements an associative array abstract data type, a structure that can map keys to values.
*   **Collision:** When two different keys map to the same hash value (and thus the same bucket).
*   **Collision Resolution Techniques:**
    *   **Separate Chaining (Open Hashing):** Each bucket stores a linked list (or other data structure) of key-value pairs that hash to that bucket.
    *   **Open Addressing (Closed Hashing):** All entries are stored in the hash table itself. When a collision occurs, alternative cells are probed until an empty cell is found.
        *   Linear Probing
        *   Quadratic Probing
        *   Double Hashing
*   **Load Factor:** The ratio of the number of stored elements to the number of buckets in the hash table ( `load_factor = n / k` where `n` is number of entries and `k` is number of buckets).
*   **Rehashing (Resizing):** When the load factor exceeds a certain threshold, the hash table is resized (usually doubled), and all existing elements are rehashed into the new, larger table.

## Time and Space Complexity (Average Case, with good hash function & collision resolution)

| Operation          | Time Complexity (Avg) | Time Complexity (Worst) | Space Complexity |
|--------------------|-----------------------|-------------------------|------------------|
| Insertion (Put)    | O(1)                  | O(n)                    | O(n)             |
| Deletion (Remove)  | O(1)                  | O(n)                    |                  |
| Search (Get)       | O(1)                  | O(n)                    |                  |

*Worst-case O(n) occurs when all keys hash to the same bucket (many collisions).*

## Implementations

*   [Python (using `dict`)](./Implementations/Python/)
*   [Java (using `HashMap`, `HashSet`)](./Implementations/Java/)
*   [C++ (using `std::unordered_map`, `std::unordered_set`)](./Implementations/Cpp/)
*   [JavaScript (using `Map`, `Set`, or plain Objects)](./Implementations/JavaScript/)

*(Contributors: Please add custom implementations or examples of using built-in hash table structures in the respective language folders.)*

## Common Applications & Problems

*   Implementing dictionaries, maps, and sets.
*   Database indexing.
*   Caching.
*   Symbol tables in compilers.
*   Cryptography (though cryptographic hash functions have stricter requirements).
*   Two Sum (using a hash map to store complements)
*   Group Anagrams
*   Longest Substring Without Repeating Characters
*   Valid Sudoku
*   ... (add more problems)

*(Contributors: Please add links to problem statements and solutions.)*

## Further Reading & Resources

*   [Link to external article/video 1]
*   [Link to external article/video 2]
