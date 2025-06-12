# Strings

## Overview

A string is traditionally a sequence of characters, either as a literal constant or as some kind of variable. The latter may allow its elements to be mutated and the length changed, or it may be fixed (after creation).

## Key Concepts

*   String Declaration and Initialization
*   Character Access and Manipulation
*   String Traversal
*   Common String Operations (Concatenation, Substring, Search, Replace, Split, Join)
*   String Comparison
*   Mutability vs. Immutability
*   Encoding (ASCII, Unicode, UTF-8)

## Time and Space Complexity (Common Operations)

*   **Accessing Character (by index):** O(1) (for most common implementations)
*   **Length:** O(1) (if stored) or O(n) (if computed)
*   **Concatenation:** O(n+m) where n and m are lengths of strings (can be O(n) if one string is appended to a mutable string buffer)
*   **Substring:** O(k) where k is the length of the substring (can vary by implementation)
*   **Search (e.g., indexOf, contains):** O(n*m) in naive cases, O(n+m) with algorithms like KMP.
*   **Space Complexity:** O(n) for the string itself.

## Implementations

*   [Python](./Implementations/Python/)
*   [Java](./Implementations/Java/)
*   [C++](./Implementations/Cpp/)
*   [JavaScript](./Implementations/JavaScript/)

*(Contributors: Please add implementations in the respective language folders.)*

## Common Problems

*   Reverse a String
*   Check for Palindrome
*   Find Longest Substring Without Repeating Characters
*   String to Integer (atoi)
*   Implement strStr()
*   Anagrams
*   ... (add more problems)

*(Contributors: Please add links to problem statements and solutions.)*

## Further Reading & Resources

*   [Link to external article/video 1]
*   [Link to external article/video 2]
