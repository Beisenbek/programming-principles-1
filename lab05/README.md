# Lab 5

## 1. Objective

This lab helps students practice their skills and better their understanding of the topics of the lecture# 5:  working with 2D arrays.

---

## 2. Tasks

### 2.1 Solve Tasks on Ejudge

Go to the ejudge system and solve the required problems.

🔗 **Lab problems**: [http://ejudge.kz/new-client?contest_id=5](http://ejudge.kz/new-client?contest_id=5)

📝 **Instructions**:
- Login with your credentials
- Solve and submit the assigned tasks
- Submit only `.cpp` files that compile and run without errors
---

## 3. What You Must Complete?

To pass this lab:

- ✅ Solve tasks successfully on [ejudge.kz](http://ejudge.kz/new-client?contest_id=5)

**Deadline**: check MS Teams announcements

---

## 4. 🛠 Troubleshooting

If you encounter issues:

- Revisit the lecture materials (github repo, lecture recording, etc.)
- Revisit the Compilation Guide
- Ask questions during the practice classes
- Bring your laptop to offline practice classes for live help

---

## 5. Quick Reference: 2D arrays

Below is a compact quick-reference for working with 2D arrays in C++: declarations, initialization, access, common patterns, and short examples.

### Declaration & initialization (static / stack)

- Fixed-size 2D array (rows x cols):
```cpp
int a[3][4];                          // 3 rows, 4 cols, uninitialized
int b[2][2] = {{1,2},{3,4}};          // nested initializer lists
int c[][3] = {{1,2,3},{4,5,6}};       // rows inferred -> 2x3
```

### Accessing elements

- Read / write: a[row][col]
- Iteration order: iterate rows outer, cols inner for best cache locality.

### Size tricks (only for static arrays)

```cpp
int rows = sizeof(a) / sizeof(a[0]);              // number of rows
int cols = sizeof(a[0]) / sizeof(a[0][0]);        // number of cols
```

### Looping

- Classic nested loops:
```cpp
for (int i = 0; i < rows; ++i)
    for (int j = 0; j < cols; ++j)
        /* use a[i][j] */;
```

- Range-based (static arrays):
```cpp
for (auto &row : a)
    for (int &x : row) x *= 2;
```


### Short examples

1) Sum all elements:
```cpp
long long sum = 0;
for (int i = 0; i < rows; ++i)
  for (int j = 0; j < cols; ++j)
    sum += a[i][j];
```

2) Transpose (square matrix, in-place):
```cpp
for (int i = 0; i < n; ++i)
  for (int j = i+1; j < n; ++j)
    std::swap(a[i][j], a[j][i]);
```

3) Fill with zeros (static arrays):
```cpp
for (int i = 0; i < rows; ++i)
  for (int j = 0; j < cols; ++j)
    a[i][j] = 0;
```

