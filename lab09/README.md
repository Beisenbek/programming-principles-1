# Lab 9

## 1. Objective

This lab helps students practice their skills and better their understanding of the topics of the lecture# 9: STL: Stack, Queue, Deque.

---

## 2. Tasks

### 2.1 Solve Tasks on Ejudge

Go to the ejudge system and solve the required problems.

🔗 **Lab problems**: [http://ejudge.kz/new-client?contest_id=9](http://ejudge.kz/new-client?contest_id=9)

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

## 4. Quick Reference: STL: Stack, Queue, Deque

Below are compact notes and short examples for stack, queue and deque.

### Stack (LIFO)
- Header: `#include <stack>`
- Type: `stack<T>` (adapter, defaults to `deque<T>` as underlying container)
- Operations:
  - `push(x)`, `pop()`, `top()`, `empty()`, `size()`
- Complexity: push/pop/top O(1)
- Notes: No iterators — access only via `top()`.

Example:
```cpp
#include <iostream>
#include <stack>

using namespace std;

int main() {
    stack<int> st;
    st.push(1); st.push(2); st.push(3);
    while (!st.empty()) {
        cout << st.top() << ' '; // prints: 3 2 1
        st.pop();
    }
    cout << '\n';
}
```

### Queue (FIFO)
- Header: `#include <queue>`
- Type: `queue<T>` (adapter, defaults to `deque<T>`)
- Operations:
  - `push(x)`, `pop()`, `front()`, `back()`, `empty()`, `size()`
- Complexity: push/pop/front/back O(1)
- Notes: No iterators — access via `front()` / `back()`.

Example:
```cpp
#include <iostream>
#include <queue>

using namespace std;

int main() {
    queue<int> q;
    q.push(1); q.push(2); q.push(3);
    while (!q.empty()) {
        cout << q.front() << ' '; // prints: 1 2 3
        q.pop();
    }
    cout << '\n';
}
```

### Deque (Double-ended queue)
- Header: `#include <deque>`
- Type: `deque<T>`
- Operations:
  - `push_back()`, `push_front()`, `pop_back()`, `pop_front()`
  - Random access: `operator[]`, `.at()`, `front()`, `back()`
  - Iterators: supports begin()/end(), rbegin()/rend()
- Complexity: push/pop at both ends O(1) amortized; random access O(1)
- Notes: Useful as a dynamic array with efficient ends operations. Can be used as the underlying container for stack/queue adapters.

Example (deque as double-ended container):
```cpp
#include <iostream>
#include <deque>

using namespace std;

int main() {
    deque<int> d;
    d.push_back(2);
    d.push_front(1); // d = {1,2}
    d.push_back(3);  // d = {1,2,3}
    for (int x : d) cout << x << ' '; // prints: 1 2 3
    cout << '\n';
    d.pop_front(); // removes 1
    d.pop_back();  // removes 3
    cout << d.front() << '\n'; // prints: 2
}
```

### Tips
- Use `deque` when you need fast insert/erase at both ends plus random access.
- Use `queue`/`stack` for clear intent and simplcity.
---
