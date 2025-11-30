# Lab 11

## 1. Objective

This lab helps students practice their skills and better their understanding of the topics of the lecture# 11: Recursion.

---

## 2. Tasks

### 2.1 Solve Tasks on Ejudge

Go to the ejudge system and solve the required problems.

🔗 **Lab problems**: [http://ejudge.kz/new-client?contest_id=9](http://ejudge.kz/new-client?contest_id=11)

📝 **Instructions**:
- Login with your credentials
- Solve and submit the assigned tasks
- Submit only `.cpp` files that compile and run without errors
- Deadline - see Info tab in contest page in ejudge
---

## 3. 🛠 Troubleshooting

If you encounter issues:

- Revisit the lecture materials (github repo, lecture recording, etc.)
- Revisit the Compilation Guide
- Ask questions during the practice classes
- Bring your laptop to offline practice classes for live help

---

## 4. Quick Reference: Recursion

Short notes and compact examples to help with recursive thinking and coding in C++.

### Recursion basics
- A recursive function calls itself.
- Two parts: base case(s) (stop) and recursive case(s) (progress towards base).
- Always ensure recursion reduces the problem (avoid infinite recursion).

### Simple examples

Factorial (classic)
```cpp
#include <iostream>

int fact(int n) {
    return (n <= 1) ? 1 : n * fact(n - 1);
}

int main() {
    std::cout << fact(5) << '\n'; // 120
}
```

Fibonacci (naive vs memoized)
```cpp
// naive exponential
int fib_naive(int n) {
    return (n <= 1) ? n : fib_naive(n-1) + fib_naive(n-2);
}

// memoized (linear)
#include <vector>
int fib_memo(int n, std::vector<int>& memo) {
    if (n <= 1) return n;
    if (memo[n] != -1) return memo[n];
    return memo[n] = fib_memo(n-1, memo) + fib_memo(n-2, memo);
}
```

Tail-recursive factorial (maintains accumulator)
```cpp
int fact_tail(int n, int acc = 1) {
    return (n <= 1) ? acc : fact_tail(n-1, acc * n);
}
```
Note: C++ does not guarantee tail-call elimination; don't rely on it for deep recursion.

### Recursion on arrays / divide-and-conquer

Sum of array (recursive)
```cpp
int sum_range(int a[], int l, int r) { // sum a[l..r]
    if (l > r) return 0;
    if (l == r) return a[l];
    int m = (l + r) / 2;
    return sum_range(a, l, m) + sum_range(a, m+1, r);
}
```

Binary search (recursive)
```cpp
int bsearch(int a[], int l, int r, int x) {
    if (l > r) return -1;
    int m = l + (r - l) / 2;
    if (a[m] == x) return m;
    return (a[m] > x) ? bsearch(a, l, m-1, x) : bsearch(a, m+1, r, x);
}
```

### Backtracking / combinatorics

Generate permutations (backtracking)
```cpp
#include <vector>
#include <algorithm>

void permute(std::vector<int>& v, int i) {
    if (i == (int)v.size()) {
        // process v
        return;
    }
    for (int j = i; j < (int)v.size(); ++j) {
        std::swap(v[i], v[j]);
        permute(v, i+1);
        std::swap(v[i], v[j]); // backtrack
    }
}


### Complexity & space
- Time complexity depends on recurrence (e.g., T(n)=2T(n/2)+O(n) → O(n log n)).
- Space: recursion uses call stack; depth = max recursion depth. Each call uses local variables.
- Stack overflow: deep recursion (e.g., >10k) may crash; use iterative solutions or increase stack where appropriate.

### Memoization
- Memoize overlapping subproblems to avoid exponential blow-up (e.g., Fibonacci).
- Use vectors / arrays / unordered_map for memo tables.

### Tips & pitfalls
- Always implement and test base cases first.
- Avoid heavy local allocations in recursive calls (prefer passing references).
- Watch for integer overflows in deep multiplications or large sums.
- Convert tail recursion to iteration if depth is large (C++ not guaranteed to optimize).
- Use recursion for clarity (trees, backtracking, divide & conquer) and iteration for tight loops or when performance/stack usage matters.
- For graph/tree problems, mark visited nodes to avoid infinite recursion.

### Quick checklist before submitting
- Correct base case(s)?
- Does each recursive call move toward the base?
- Are side effects (mutations) intended and safe?
- Is memoization needed to meet time limits?
- Will recursion depth exceed platform limits? If yes, rewrite iteratively.

---