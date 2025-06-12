# Bit Manipulation

## Overview

Bit manipulation is the act of algorithmically manipulating bits or other pieces of data shorter than a word. This technique is used for a variety of tasks such as low-level device control, error detection and correction algorithms, data compression, encryption algorithms, and optimization. For competitive programming and software engineering, it often provides efficient ways to solve problems related to sets, numbers, and state representation.

## Key Concepts & Operators

*   **Binary Representation:** Understanding how numbers are represented in binary (base-2).
*   **Bitwise Operators:**
    *   **AND (`&`):** `1 & 1 = 1`, `1 & 0 = 0`, `0 & 1 = 0`, `0 & 0 = 0`.
        *   Use: Check if a bit is set, clear a bit.
    *   **OR (`|`):** `1 | 1 = 1`, `1 | 0 = 1`, `0 | 1 = 1`, `0 | 0 = 0`.
        *   Use: Set a bit.
    *   **XOR (`^`):** `1 ^ 1 = 0`, `1 ^ 0 = 1`, `0 ^ 1 = 1`, `0 ^ 0 = 0`.
        *   Properties: `x ^ x = 0`, `x ^ 0 = x`, `x ^ y = y ^ x` (commutative), `(x ^ y) ^ z = x ^ (y ^ z)` (associative).
        *   Use: Toggle a bit, find the number that appears once, swap two numbers without a temp variable.
    *   **NOT (`~`):** Inverts all bits (0s become 1s, 1s become 0s). `~0101 = 1010` (representation depends on integer size and signedness).
    *   **Left Shift (`<<`):** `x << k` shifts bits of `x` to the left by `k` positions, filling new rightmost bits with 0. Equivalent to `x * 2^k`.
    *   **Right Shift (`>>`):** `x >> k` shifts bits of `x` to the right by `k` positions.
        *   **Arithmetic Right Shift:** Fills new leftmost bits with the sign bit (preserves sign for signed numbers). Common in C++/Java for signed types.
        *   **Logical Right Shift (`>>>` in Java/JavaScript):** Fills new leftmost bits with 0. Python's `>>` is arithmetic for negative numbers.

## Common Bitwise Operations & Tricks

Let `n` be an integer and `k` be the bit position (0-indexed from the right).

1.  **Check if the k-th bit is set:**
    *   `if (n & (1 << k)) != 0:`
2.  **Set the k-th bit:**
    *   `n = n | (1 << k)`
3.  **Clear (unset) the k-th bit:**
    *   `n = n & ~(1 << k)`
4.  **Toggle the k-th bit:**
    *   `n = n ^ (1 << k)`
5.  **Get the value of the last set bit (LSB) / Rightmost set bit:**
    *   `lsb = n & (-n)`  (due to two's complement representation)
    *   Example: `n = 12 (0...01100)`, `-n = (0...01100)` -> `(1...10011)` (invert) -> `(1...10100)` (add 1). `n & -n = 4 (0...00100)`.
6.  **Clear the last set bit (LSB):**
    *   `n = n & (n - 1)`
7.  **Check if a number is a power of 2:**
    *   `if (n > 0 && (n & (n - 1)) == 0):` (A power of 2 has only one bit set, e.g., 01000. `n-1` will be 00111. `n & (n-1)` will be 0).
8.  **Count the number of set bits (Hamming Weight / Population Count):**
    *   Loop and check each bit: O(log n) or O(number of bits).
    *   Brian Kernighan's Algorithm: `count = 0; while(n > 0) { n &= (n-1); count++; }` O(number of set bits).
    *   Built-in functions: `__builtin_popcount` (C++ GCC), `Integer.bitCount` (Java).
9.  **Swap two numbers without a temporary variable:**
    *   `a = a ^ b;`
    *   `b = a ^ b; // b = (a^b)^b = a`
    *   `a = a ^ b; // a = (a^b)^a = b`
10. **Isolate the k-th bit (get its value, 0 or 2<sup>k</sup>):**
    *   `kth_bit_value = n & (1 << k)`
11. **Create a mask with the lower `k` bits set:**
    *   `mask = (1 << k) - 1` (e.g., for k=3, `(1<<3)-1 = 8-1 = 7 (0111)`)

## Applications

*   **Representing Sets:** A bitmask of length `N` can represent any subset of `N` items. If the i-th bit is set, the i-th item is in the subset.
    *   Union: `mask1 | mask2`
    *   Intersection: `mask1 & mask2`
    *   Complement (relative to a full mask): `full_mask ^ mask`
    *   Iterating through all subsets: `for (int i = 0; i < (1 << N); ++i)`
*   **Dynamic Programming with Bitmasks (DP on Subsets):** Solve problems where states depend on subsets of items.
*   **Optimizing calculations:** Multiplication/division by powers of 2.
*   **Low-level programming:** Device drivers, embedded systems.
*   **Graphics:** Color representation, bit blitting.
*   **Cryptography and Hashing.**
*   **Solving specific algorithmic problems efficiently:**
    *   Finding the single non-repeating element in an array where others repeat twice (XOR all elements).
    *   Finding two non-repeating elements.
    *   Checking parity (even/odd number of set bits).

## Implementations & Examples

*   [Python](./Implementations/Python/)
*   [Java](./Implementations/Java/)
*   [C++](./Implementations/Cpp/)
*   [JavaScript](./Implementations/JavaScript/)

*(Contributors: Please add examples of common bit manipulation techniques and problems.)*

## Further Reading & Resources

*   [Bit Manipulation (CP-Algorithms)](https://cp-algorithms.com/algebra/bit_manipulation.html)
*   [GeeksforGeeks Bitwise Hacks for Competitive Programming](https://www.geeksforgeeks.org/bitwise-hacks-for-competitive-programming/)
*   [Bit Twiddling Hacks (Stanford Graphics)](https://graphics.stanford.edu/~seander/bithacks.html)
