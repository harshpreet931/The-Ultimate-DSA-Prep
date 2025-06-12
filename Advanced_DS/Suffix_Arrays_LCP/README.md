# Suffix Arrays & LCP Arrays

## Suffix Array

### Overview

A Suffix Array is a sorted array of all suffixes of a given string. It's a powerful data structure used in string processing algorithms, particularly for tasks involving pattern searching, string matching, and analyzing string properties.

Let `S` be a string of length `n`. A suffix of `S` starting at index `i` is `S[i...n-1]`.
The suffix array `SA` is an array of integers of length `n` that stores the starting indices of all suffixes of `S` in lexicographical (alphabetical) order.
That is, `S[SA[0]...n-1] < S[SA[1]...n-1] < ... < S[SA[n-1]...n-1]`.

### Example

String `S = "banana"`
Suffixes:
0: "banana"
1: "anana"
2: "nana"
3: "ana"
4. "na"
5: "a"

Sorted Suffixes:
"a"       (index 5)
"ana"     (index 3)
"anana"   (index 1)
"banana"  (index 0)
"na"      (index 4)
"nana"    (index 2)

Suffix Array `SA = [5, 3, 1, 0, 4, 2]`

### Construction

Constructing a suffix array efficiently is non-trivial.
*   **Naive Approach:** Generate all suffixes and sort them. O(n<sup>2</sup> log n) or O(n<sup>2</sup>) with string-specific sorting. Too slow for large strings.
*   **Efficient Algorithms:**
    *   **O(n log<sup>2</sup> n):** Based on comparing prefixes of increasing lengths (doubling trick).
    *   **O(n log n):** Further refinements of the doubling trick.
    *   **O(n):** Linear time algorithms like SA-IS (Skew Algorithm) or DC3 (Difference Cover). These are more complex to implement.

### Applications

*   **Pattern Searching (Exact String Matching):** Find occurrences of a pattern `P` in `S`. Binary search for `P` on the suffix array. O(m log n) where `m` is pattern length. Can be improved to O(m + log n) using LCP array.
*   **Longest Common Prefix (LCP) between two suffixes.**
*   **Longest Repeated Substring.**
*   **Longest Common Substring of two strings.** (Concatenate strings with a special separator).
*   **Number of distinct substrings.**
*   Bioinformatics (e.g., DNA sequence alignment).

---

## LCP Array (Longest Common Prefix Array)

### Overview

The LCP Array is an auxiliary data structure often used in conjunction with a Suffix Array. The LCP array `LCP` is an array of integers of length `n` where `LCP[i]` stores the length of the longest common prefix between the suffix `S[SA[i]...n-1]` and the suffix `S[SA[i-1]...n-1]`.
By definition, `LCP[0]` is usually undefined or set to 0.

So, `LCP[i] = length(LCP(S[SA[i]...], S[SA[i-1]...]))` for `i > 0`.

### Example (Continuing from `S = "banana"`, `SA = [5, 3, 1, 0, 4, 2]`)

Sorted Suffixes:
`SA[0]=5`: "a"
`SA[1]=3`: "ana"        LCP("a", "ana") = 1 ("a") -> `LCP[1]=1`
`SA[2]=1`: "anana"      LCP("ana", "anana") = 3 ("ana") -> `LCP[2]=3`
`SA[3]=0`: "banana"     LCP("anana", "banana") = 0 -> `LCP[3]=0`
`SA[4]=4`: "na"         LCP("banana", "na") = 0 -> `LCP[4]=0`
`SA[5]=2`: "nana"       LCP("na", "nana") = 2 ("na") -> `LCP[5]=2`

LCP Array `LCP = [undef, 1, 3, 0, 0, 2]` (or `[0, 1, 3, 0, 0, 2]`)

### Construction

*   **Kasai's Algorithm:** An efficient O(n) algorithm to construct the LCP array given the string `S` and its Suffix Array `SA`.
    *   It utilizes the `rank` array (inverse of `SA`, where `rank[i]` is the lexicographical rank of suffix `S[i...]`).
    *   It processes suffixes in the order of their starting positions in the original string.
    *   The key idea is that if `LCP(S[SA[rank[i]]], S[SA[rank[i]-1]]) = h`, then `LCP(S[SA[rank[i+1]]], S[SA[rank[i+1]-1]])` is at least `h-1`.

### Applications (often combined with Suffix Array)

*   **Longest Repeated Substring:** The maximum value in the LCP array.
*   **Number of Distinct Substrings:** `Sum_{i=0}^{n-1} (n - SA[i]) - Sum_{i=1}^{n-1} LCP[i]`. Each suffix `S[SA[i]...]` introduces `(n - SA[i])` substrings, but `LCP[i]` of them are duplicates from `S[SA[i-1]...]`.
*   **Longest Common Substring of Multiple Strings:** Construct a generalized suffix array for concatenated strings.
*   **Building Suffix Trees/Suffix Automata:** Can be used as an intermediate step or for understanding relationships.
*   **Range Minimum Query (RMQ) on LCP Array:** Can find LCP between any two arbitrary suffixes `S[i...]` and `S[j...]` in O(1) after O(n log n) or O(n) preprocessing. `LCP(S[i...], S[j...]) = RMQ(LCP, rank[i]+1, rank[j])` (assuming `rank[i] < rank[j]`).

## Implementations

*   **Suffix Array Construction:**
    *   [Python](./Implementations/Python/suffix_array.py)
    *   [Java](./Implementations/Java/SuffixArray.java)
    *   [C++](./Implementations/Cpp/suffix_array.cpp)
    *   [JavaScript](./Implementations/JavaScript/suffixArray.js)
*   **LCP Array Construction (Kasai's Algorithm):**
    *   [Python](./Implementations/Python/lcp_array_kasai.py)
    *   [Java](./Implementations/Java/LCPArrayKasai.java)
    *   [C++](./Implementations/Cpp/lcp_array_kasai.cpp)
    *   [JavaScript](./Implementations/JavaScript/lcpArrayKasai.js)

*(Contributors: Please add implementations, focusing on O(n log n) or O(n log^2 n) for Suffix Array and Kasai's for LCP.)*

## Further Reading & Resources

*   [Suffix Array (CP-Algorithms)](https://cp-algorithms.com/string/suffix-array.html)
*   [GeeksforGeeks articles on Suffix Array and LCP Array](https://www.geeksforgeeks.org/suffix-array-set-1-introduction/)