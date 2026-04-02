# Binary Search

## Template

```
public int findBoundary(int[] nums, int threshold) {
    int left = MIN_POSSIBLE_VAL; 
    int right = MAX_POSSIBLE_VAL;
    int ans = right;

    while (left <= right) {
        int mid = left + (right - left) / 2;

        if (check(mid)) { // If this value works...
            ans = mid;    // Record it as a potential answer
            right = mid - 1; // Try to find something even smaller
        } else {
            left = mid + 1;  // Too small, must increase capacity
        }
    }
    return ans; 
}

```

# Binary Search Intuition Cheat Sheet

Binary search isn't just for sorted arrays; it’s a powerful tool for any problem where the search space is predictable. Use these three "signals" to identify when to use it.

## 1. Sorted Array (The "Classical" Search)
*   **The Scenario:** You have a fixed, pre-ordered set of data.
*   **The Intuition:** Because it's sorted, one comparison tells you which half of the data is irrelevant.
*   **Common Use Case:** Finding a specific number or the insertion point in a list.
*   **Complexity:** $O(\log N)$

## 2. Monotonicity (The "Yes/No" Boundary)
*   **The Scenario:** The input (like `weights[]`) might not be sorted, but the **answer space** (possible capacities) is.
*   **The Intuition:** If a value $X$ works, then every value *greater* than $X$ will also work (or vice versa). This creates a transition point:
    *   `[False, False, False, True, True, True]`
    *   Your goal is to find the **first `True`** (minimum) or **last `False`** (maximum).
*   **Complexity:** $O(N \log (\text{Range}))$ — where $N$ is the cost of your `check()` function.

## 3. Keywords (The "Pattern" Search)
Look for these specific phrases in the problem description. They almost always signal a Binary Search on the answer:
*   **"Minimize the maximum..."** (e.g., Minimize the maximum ship capacity)
*   **"Maximize the minimum..."** (e.g., Maximize the minimum distance between cows)
*   **"Find the smallest/largest value that satisfies..."**
*   **"The threshold is $K$..."**

---

    

## Questions:-

 - [capacity-to-ship-packages-within-d-days](https://leetcode.com/problems/capacity-to-ship-packages-within-d-days/)
 - [koko-eating-bananas](https://leetcode.com/problems/koko-eating-bananas/)
