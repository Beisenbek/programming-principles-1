# Lab 8

## 1. Objective

This lab helps students practice their skills and better their understanding of the topics of the lecture# 8: STL: Algorithms, Containers(Vector, Set, Map), Iterators.

---

## 2. Tasks

### 2.1 Solve Tasks on Ejudge

Go to the ejudge system and solve the required problems.

🔗 **Lab problems**: [http://ejudge.kz/new-client?contest_id=8](http://ejudge.kz/new-client?contest_id=8)

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

## 4. Quick Reference: STL: Algorithms, Containers(Vector, Set, Map), Iterators

### Vector
```cpp
#include <vector>
vector<int> v;                // empty vector
vector<int> v(5);            // size 5, values = 0
vector<int> v(5, 2);         // size 5, values = 2
vector<int> v = {1,2,3,4,5}; // initialization list
```

#### Common vector operations
```cpp
v.push_back(x);     // append to end
v.pop_back();       // remove last element
v.size();          // number of elements
v.empty();         // test if empty
v[i];              // access element (no bounds check)
v.at(i);           // access with bounds check
v.front();         // first element
v.back();          // last element
v.clear();         // remove all elements
```

#### Vector iteration
```cpp
// C++11 range-based for
for (int x : v) cout << x << ' ';

// Iterator-based
for (vector<int> :: iterator it = v.begin(); it != v.end(); ++it) {
    cout << *it << ' ';
}
```

### Set
```cpp
#include <set>
set<int> s;                  // empty set
set<int> s = {1,2,3,4,5};   // initialization list

// Common operations
s.insert(x);        // insert element
s.erase(x);         // remove element
s.count(x);         // 1 if present, 0 if not
s.find(x);          // iterator to element or s.end()
s.size();          // number of elements
```

### Map
```cpp
#include <map>
map<string, int> m;          // empty map
m["key"] = 42;                    // insert/update
m.count("key");                   // 1 if present
map<string, int> :: iterator it = m.find("key");         // iterator to element
if (it != m.end()) cout << it->second;
```

### Common Algorithms
```cpp
#include <algorithm>

// Sorting
sort(v.begin(), v.end());                    // ascending
sort(v.begin(), v.end(), greater<int>());    // descending

```

### Iterators
- begin(): first element
- end(): one past last element
- rbegin(): first element in reverse
- rend(): one past last in reverse

### Short Examples

1) Vector basics
```cpp
vector<int> v = {1, 2, 3, 4, 5};
v.push_back(6);                // add 6 to end
cout << v.back() << '\n';      // prints 6
v.pop_back();                  // removes 6
```

2) Set operations
```cpp
set<int> s = {3, 1, 4, 1, 5};  // stores {1, 3, 4, 5}
s.insert(2);                    // now {1, 2, 3, 4, 5}
if (s.count(3)) cout << "found 3\n";
```

3) Map usage
```cpp
map<string, int> scores;
scores["Alice"] = 100;
scores["Bob"] = 90;
for (const auto& [name, score] : scores) {
    cout << name << ": " << score << '\n';
}
```

### Tips
- Use vector as your default container
- Use can auto for iterator types instead declaring full type. I.e:
```
//instead
for (vector<int> :: iterator it = v.begin(); it != v.end(); ++it) {
    cout << *it << ' ';
}
//you can write:
for (auto it = v.begin(); it != v.end(); ++it) {
    cout << *it << ' ';
}
```
- Remember that iterators can be invalidated by container modifications
- Check container documentation for complexity guarantees
