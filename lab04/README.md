# Lab 4

## 1. Objective

This lab helps students practice their skills and better their understanding of the topics of the lecture# 4:  working with 1D arrays.

---

## 2. Tasks

### 2.1 Solve Tasks on Ejudge

Go to the ejudge system and solve the required problems.

🔗 **Lab problems**: [http://ejudge.kz/new-client?contest_id=4](http://ejudge.kz/new-client?contest_id=4)

📝 **Instructions**:
- Login with your credentials
- Solve and submit the assigned tasks
- Submit only `.cpp` files that compile and run without errors
---

## 3. What You Must Complete?

To pass this lab:

- ✅ Solve tasks successfully on [ejudge.kz](http://ejudge.kz/new-client?contest_id=4)

**Deadline**: check MS Teams announcements

---

## 4. 🛠 Troubleshooting

If you encounter issues:

- Revisit the lecture materials (github repo, lecture recording, etc.)
- Revisit the Compilation Guide
- Ask questions during the practice classes
- Bring your laptop to offline practice classes for live help

---

## 5. Quick Reference: 1D arrays

Below is a compact quick-reference for working with 1D arrays in C++: declarations, initialization, access, common patterns, and short examples.

### Declaration & initialization

- Fixed-size (stack):

```cpp
int a[5];           // uninitialized (contains garbage)
int b[5] = {1,2,3}; // remaining elements are zero-initialized -> {1,2,3,0,0}
int c[] = {4,5,6};  // size inferred -> size 3
```

### Accessing elements

- Read / write by index (0-based): `a[0]`, `a[i]`

### Size of an array

- At compile-time for static arrays:

```cpp
int n = sizeof(a) / sizeof(a[0]); // only works for arrays, not pointers
```

### Looping

- Classic for-loop:

```cpp
for (int i = 0; i < n; ++i) {
		// use a[i]
}
```

- Range-based for (read-only or to modify elements directly):

```cpp
for (int &x : a) x *= 2;    // modifies elements
for (int x : a) cout << x; // read-only copy
```

### Short examples

1) Sum elements:

```cpp
int sum = 0;
for (int x : a) sum += x;
```

2) Reverse in-place:

```cpp
for (int i = 0; i < n/2; ++i) swap(a[i], a[n-1-i]);
```