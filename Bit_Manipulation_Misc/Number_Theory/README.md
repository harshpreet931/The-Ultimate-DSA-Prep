# Number Theory

## Overview

Number theory is a branch of pure mathematics devoted primarily to the study of integers and integer-valued functions. In competitive programming and computer science, number theory concepts are crucial for solving problems related to divisibility, prime numbers, modular arithmetic, and more.

## Key Concepts and Algorithms

1.  **Divisibility & Greatest Common Divisor (GCD) / Highest Common Factor (HCF):**
    *   `a | b` means `a` divides `b`.
    *   **Euclidean Algorithm:** Efficiently computes `gcd(a, b)`.
        *   `gcd(a, b) = gcd(b, a % b)`
        *   Base case: `gcd(a, 0) = a`.
    *   **Least Common Multiple (LCM):** `lcm(a, b) = (a * b) / gcd(a, b)`.
    *   **Extended Euclidean Algorithm:** Finds integers `x` and `y` such that `ax + by = gcd(a, b)`. Crucial for finding modular multiplicative inverse.

2.  **Prime Numbers:**
    *   A natural number greater than 1 that has no positive divisors other than 1 and itself.
    *   **Primality Test:**
        *   Trial Division: Check divisibility from 2 up to `sqrt(n)`. O(sqrt(n)).
        *   Sieve of Eratosthenes: Finds all primes up to `n`. O(n log log n).
        *   Miller-Rabin Primality Test: A probabilistic test, very fast and accurate for large numbers.
    *   **Prime Factorization:** Expressing a number as a product of its prime factors.
        *   Trial division up to `sqrt(n)`.

3.  **Modular Arithmetic:**
    *   Arithmetic operations performed within a modulus `m`. `(a + b) mod m`, `(a - b) mod m`, `(a * b) mod m`.
    *   **Modular Exponentiation (Binary Exponentiation):** Computes `(base^exponent) % modulus` efficiently. O(log exponent).
    *   **Modular Multiplicative Inverse:** For an integer `a` and modulus `m`, its modular multiplicative inverse `a^-1` is an integer `x` such that `(a * x) % m = 1`.
        *   Exists if and only if `gcd(a, m) = 1` (i.e., `a` and `m` are coprime).
        *   Can be found using:
            *   Extended Euclidean Algorithm: `ax + my = gcd(a,m) = 1`. Then `x % m` is the inverse.
            *   Fermat's Little Theorem (if `m` is prime): `a^(m-2) % m`.
            *   Euler's Totient Theorem (if `m` is not necessarily prime): `a^(φ(m)-1) % m`.

4.  **Euler's Totient Function (φ(n)):**
    *   Counts the number of positive integers up to `n` that are relatively prime to `n`.
    *   If `n = p1^a1 * p2^a2 * ... * pk^ak` is the prime factorization of `n`, then
        `φ(n) = n * (1 - 1/p1) * (1 - 1/p2) * ... * (1 - 1/pk)`.
    *   Property: `a^φ(m) ≡ 1 (mod m)` if `gcd(a, m) = 1` (Euler's Totient Theorem).

5.  **Fermat's Little Theorem:**
    *   If `p` is a prime number, then for any integer `a` not divisible by `p`, we have `a^(p-1) ≡ 1 (mod p)`.
    *   A common corollary: `a^p ≡ a (mod p)` for any integer `a` and prime `p`.

6.  **Chinese Remainder Theorem (CRT):**
    *   Solves a system of simultaneous congruences with pairwise coprime moduli.
    *   If we have:
        `x ≡ a1 (mod m1)`
        `x ≡ a2 (mod m2)`
        ...
        `x ≡ ak (mod mk)`
        where `m1, m2, ..., mk` are pairwise coprime, CRT provides a unique solution for `x` modulo `M = m1*m2*...*mk`.

7.  **Combinatorics (related to Number Theory):**
    *   **Binomial Coefficients (`nCr` or `C(n, r)`):** Number of ways to choose `r` items from `n` items. `nCr = n! / (r! * (n-r)!)`.
    *   Computing `nCr % p` (where `p` is prime):
        *   Use Lucas Theorem if `p` is small.
        *   Precompute factorials and inverse factorials modulo `p`.
    *   **Catalan Numbers:** Sequence of natural numbers that occur in various counting problems.
    *   **Inclusion-Exclusion Principle.**

8.  **Other Topics:**
    *   **Diophantine Equations:** Equations where only integer solutions are sought.
    *   **Fibonacci Numbers and Properties (e.g., Pisano periods).**
    *   **Integer Factorization Algorithms (for larger numbers, e.g., Pollard's Rho).**

## Applications

*   Cryptography (RSA, Diffie-Hellman).
*   Hashing algorithms.
*   Generating pseudo-random numbers.
*   Solving a wide range of competitive programming problems involving counting, divisibility, and modular arithmetic.
*   Error-correcting codes.

## Implementations & Examples

*   [Python](./Implementations/Python/)
*   [Java](./Implementations/Java/)
*   [C++](./Implementations/Cpp/)
*   [JavaScript](./Implementations/JavaScript/)

*(Contributors: Please add implementations for GCD, Sieve, Modular Exponentiation, Modular Inverse, CRT, etc.)*

## Further Reading & Resources

*   [Number Theory (CP-Algorithms)](https://cp-algorithms.com/algebra/primality_tests.html) (and other sections on number theory)
*   [GeeksforGeeks Number Theory Articles](https://www.geeksforgeeks.org/number-theory-interesting-facts-and-algorithms/)
*   Project Euler problems often involve number theory.
