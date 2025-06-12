# Game Theory and Mathematical Algorithms

## Game Theory

### Overview

Game theory is the study of mathematical models of strategic interaction among rational decision-makers. It has applications in many fields, including economics, political science, psychology, logic, computer science, and biology. In competitive programming, game theory problems often involve impartial games, where the available moves depend only on the state of the game, not on which player is moving.

### Key Concepts in Impartial Games

*   **Impartial Game:** A game in which the available moves from any position depend only on the position itself, not on whose turn it is. Examples: Nim, Tic-Tac-Toe (if no player owns pieces), Chess (is partial).
*   **Winning and Losing Positions (P-positions and N-positions):**
    *   **P-position (Previous player winning):** A state from which every move leads to an N-position. The player who just moved to this state will win if the other player plays optimally.
    *   **N-position (Next player winning):** A state from which there is at least one move leading to a P-position. The player whose turn it is to move from this state will win if they play optimally.
    *   A terminal position (no moves possible) is a P-position.
*   **Sprague-Grundy Theorem:**
    *   Every impartial game under the normal play convention (last player to move wins) is equivalent to a Nim pile of a certain size. This size is called the **Grundy number (g-number)** or **nim-value (nimber)** of the game state.
    *   `g(state) = mex({g(next_state_1), g(next_state_2), ...})`
    *   **mex (Minimum Excluded value):** For a set of non-negative integers, `mex(S)` is the smallest non-negative integer not in `S`. E.g., `mex({0,1,3}) = 2`.
    *   A state is a P-position if and only if its g-number is 0.
    *   A state is an N-position if and only if its g-number is non-zero.
*   **Sum of Games (Composite Games):** If a game is composed of several independent subgames (e.g., Nim with multiple piles), the g-number of the composite game is the XOR sum of the g-numbers of its subgames.
    *   `g(game1 + game2 + ... + gameK) = g(game1) ^ g(game2) ^ ... ^ g(gameK)`
    *   The composite game is a P-position if this XOR sum is 0.

### Common Game Theory Problems

*   **Nim Game:** Given several piles of stones, two players take turns removing any number of stones (at least one) from a single pile. The player who takes the last stone wins.
    *   Solution: The game is a P-position if the XOR sum of the pile sizes is 0. Otherwise, it's an N-position.
*   **Games on Graphs:** Taking turns moving a token on a DAG. The g-number of a node `u` is `mex` of g-numbers of its neighbors.
*   **Subtraction Games:** A game where players subtract a number from a set of allowed numbers from a pile.
*   **Take-Away Games:** Variations of Nim.

---

## Mathematical Algorithms (Miscellaneous)

This section covers various mathematical algorithms and concepts not fitting neatly elsewhere but useful in problem-solving.

### 1. Geometry Basics

*   **Points, Lines, Segments:** Representations, distance, slope, intersection.
*   **Convex Hull:** Smallest convex polygon containing a set of points. Algorithms: Graham scan, Monotone Chain (O(n log n)).
*   **Area of a Polygon:** Shoelace formula.
*   **Sweep Line Algorithms:** An algorithmic paradigm that uses a conceptual sweep line to solve geometric problems.

### 2. Matrix Operations

*   **Matrix Exponentiation:** Efficiently compute `M^k` for a matrix `M` in O(d<sup>3</sup> log k) time, where `d` is dimension of matrix. Used for solving linear recurrence relations (e.g., Fibonacci), counting paths in graphs.
*   **Gaussian Elimination:** Solving systems of linear equations.

### 3. Probability and Expected Value

*   **Basic Probability:** Calculating probabilities of events.
*   **Expected Value (EV):** `EV = sum(value_of_outcome * probability_of_outcome)`.
    *   **Linearity of Expectation:** `E[X + Y] = E[X] + E[Y]`, even if X and Y are not independent. Very powerful.
*   **Randomized Algorithms:** Algorithms that use randomness (e.g., randomized quicksort, primality testing).

### 4. Fast Fourier Transform (FFT) / Number Theoretic Transform (NTT)

*   **Polynomial Multiplication:** FFT/NTT can multiply two polynomials of degree `n` in O(n log n) time.
*   **Convolution:** Used for signal processing, image processing, and multiplying large integers.
*   NTT is used when operations need to be done modulo a prime, avoiding floating-point precision issues of FFT.

### 5. Miscellaneous Mathematical Concepts

*   **Fibonacci Numbers:** Properties, matrix form.
*   **Catalan Numbers:** Counting problems (e.g., balanced parentheses, triangulations).
*   **Stirling Numbers:** Counting permutations and partitions.
*   **Inclusion-Exclusion Principle:** Counting elements in union of sets.
*   **Pigeonhole Principle.**
*   **Meet-in-the-Middle:** A technique that divides a problem into two halves, solves them independently, and then combines the results. Often reduces exponential complexity (e.g., from O(2<sup>n</sup>) to O(2<sup>n/2</sup>)).

## Implementations & Examples

*   **Game Theory:**
    *   [Python](./Implementations/Python/nim_game.py)
    *   [Java](./Implementations/Java/NimGame.java)
*   **Mathematical Algorithms:**
    *   [Python](./Implementations/Python/matrix_exponentiation.py)
    *   [Java](./Implementations/Java/MatrixExponentiation.java)
    *   (Implementations for Convex Hull, FFT, etc., can be added)

*(Contributors: Please add examples for Sprague-Grundy, common game types, and various mathematical algorithms.)*

## Further Reading & Resources

*   **Game Theory:**
    *   [Winning Ways for your Mathematical Plays (Book by Berlekamp, Conway, Guy)]
    *   [CP-Algorithms: Games on DAGs, Sprague-Grundy Theorem](https://cp-algorithms.com/game_theory/sprague_grundy_theorem.html)
*   **Mathematical Algorithms:**
    *   [CP-Algorithms (various sections on Algebra, Geometry, Miscellaneous)]
    *   [Competitive Programmer's Handbook (Sections on Mathematics)](https://cses.fi/book/book.pdf)
