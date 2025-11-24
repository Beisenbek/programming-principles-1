# Lab 10

## 1. Objective

This lab helps students practice their skills and better their understanding of the topics of the lecture# 10: Comparators. Struct.

---

## 2. Tasks

### 2.1 Solve Tasks on Ejudge

Go to the ejudge system and solve the required problems.

🔗 **Lab problems**: [http://ejudge.kz/new-client?contest_id=9](http://ejudge.kz/new-client?contest_id=10)

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

## 4. Quick Reference: Comparators & Structs

### struct basics
- Simple aggregate:
```cpp
struct Point {
    int x;
    int y;
};
```
- With constructor and methods:
```cpp
struct Person {
    std::string name;
    int age;
    Person(std::string n, int a) : name(n), age(a) {}
};
```

### Overloading comparison operators
- Provide operator< for natural ordering:
```cpp
bool operator<(const Person& a, const Person& b) {
    return std::tie(a.name, a.age) < std::tie(b.name, b.age);
}
```
- operator== for equality (useful for containers that check equality).

### Custom comparators (for sort, set, map)
- Lambda comparator for sort:
```cpp
std::vector<Person> v = { /*...*/ };
std::sort(v.begin(), v.end(), [](const Person &a, const Person &b){
    return a.age < b.age; // sort by age ascending
});
```
- Functor comparator (for ordered containers):
```cpp
struct ByName {
    bool operator()(const Person &a, const Person &b) const {
        return a.name < b.name;
    }
};
std::set<Person, ByName> s;
```
- Inline struct comparator for std::map:
```cpp
std::map<Person,int, ByName> m;
```

### Contiguous-key comparator (strict weak ordering)
- Comparator must implement strict weak ordering:
  - If comp(a,b) is true, comp(b,a) must be false.
  - No contradictions across elements.
- Prefer using std::tie for lexicographic order:
```cpp
return std::tie(a.x, a.y) < std::tie(b.x, b.y);
```

### Examples

1) Sort points by x, then y:
```cpp
struct Point { int x,y; };
std::vector<Point> pts = { {1,2}, {1,1}, {0,5} };
std::sort(pts.begin(), pts.end(), [](const Point &a,const Point &b){
    return std::tie(a.x,a.y) < std::tie(b.x,b.y);
});
```

2) Use map with custom ordering (by age desc):
```cpp
struct ByAgeDesc {
    bool operator()(const Person &a, const Person &b) const {
        return a.age > b.age;
    }
};
std::map<Person,int,ByAgeDesc> leaderboard;
```

### Tips & pitfalls
- Use std::tie to compare multiple fields concisely and correctly.
- Do not use functors or comparators that depend on mutable state unless intentional.
- Remember comparator semantics: return true if first is "less" than second.
- For containers (set/map) comparator must be consistent for lifetime of container keys.
- Prefer passing comparators as templates or lambdas to std::sort for clarity.

---