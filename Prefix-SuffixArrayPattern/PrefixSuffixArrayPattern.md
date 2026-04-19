# How to identify DSA patterns and build intuition

## 1. First ask: what is the problem asking?

Before jumping into code, identify:

- **Input type**: array, string, tree, graph, matrix
- **Output type**: single value, boolean, index, subarray, path
- **Constraints**: small or large `n`
- **Goal**: find, count, optimize, compare, search

---

## 2. Look for pattern clues

### Common clues and matching patterns

| Clue in problem | Likely pattern |
|---|---|
| "subarray", "contiguous" | Sliding Window, Prefix Sum |
| "smallest/largest index" | Binary Search, Two Pointers |
| "next greater/smaller" | Monotonic Stack |
| "before/after each index" | Prefix/Suffix Array |
| "reuse overlapping subproblems" | DP |
| "tree path / ancestor" | DFS, BFS, Tree recursion |
| "shortest path" | BFS, Dijkstra |
| "connected components" | DFS/BFS, Union Find |

---

## 3. Write the intuition in simple words

Use this format:

### Intuition template
- What do I need to compute?
- What makes brute force slow?
- Can I precompute something?
- Can I keep track of a running value?
- Can I reduce repeated work?

### Example
For prefix/suffix problems:

- I need the left max and right min for every index
- Recomputing them for every index is expensive
- So I precompute prefix max and suffix min
- Then I check each index in one pass

---

## 4. Notes format for each problem

Keep a consistent structure like this:

```md
# Problem Name

## Pattern
Prefix-Suffix Array

## Intuition
Explain in 2–4 lines what the idea is.

## Approach
1. Precompute ...
2. Traverse ...
3. Check condition ...

## Edge Cases
- Empty array
- Single element
- All same values
- No valid answer

## Complexity
- Time: O(n)
- Space: O(n)

## Key takeaway
What pattern did this problem teach me?
