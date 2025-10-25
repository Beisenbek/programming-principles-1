# Lab 7

## 1. Objective

This lab helps students practice their skills and better their understanding of the topics of the lecture# 7:  Functions.

---

## 2. Tasks

### 2.1 Solve Tasks on Ejudge

Go to the ejudge system and solve the required problems.

🔗 **Lab problems**: [http://ejudge.kz/new-client?contest_id=7](http://ejudge.kz/new-client?contest_id=7)

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

## 4. Quick Reference: Functions

A compact reference for defining, using, and passing functions in C++.

### Declaration vs Definition
- Prototype (declaration): tells compiler a function exists.
  ```cpp
  int add(int a, int b); // declaration
  ```
- Definition: provides implementation.
  ```cpp
  int add(int a, int b) { return a + b; } // definition
  ```

### Parameter passing
- By value: copies argument (safe for small types).
  ```cpp
  void f(int x);
  ```
- By reference: modifies caller's object, no copy.
  ```cpp
  void swap(int &a, int &b);
  ```
- By const reference: efficient read-only access for large objects.
  ```cpp
  void print(const string &s);
  ```
- By pointer: similar to reference, allows null check.
  ```cpp
  void process(int *p);
  ```

### Passing arrays
- Arrays decay to pointers; size lost unless passed separately.
  ```cpp
  void process(int a[], int n);
  void process(int *a, int n);
  ```

### Small examples

1) Sum elements (array parameter)
```cpp
#include <iostream>

using namespace std;

void process(int a[], int n) {
    long long sum = 0;
    for (int i = 0; i < n; ++i) sum += a[i];
    cout << sum << endl;
}

int main() {
    int arr[] = {1, 2, 3, 4};
    process(arr, 4); // prints 10
    return 0;
}
```

```cpp
#include <iostream>

using namespace std;

void process(int *a, int n) {
    for (int i = 0; i < n; ++i) a[i] *= 2;
}

int main() {
    int arr[] = {1, 2, 3, 4};
    process(arr, 4); // arr becomes {2,4,6,8}
    for (int x : arr) 
        cout << x << ' ';
    cout << endl;

    // Passing a subarray (pointer arithmetic)
    process(arr + 1, 2); // modifies elements at indices 1 and 2
    for (int x : arr) 
        cout << x << ' ';
    cout << endl;
    return 0;
}
```