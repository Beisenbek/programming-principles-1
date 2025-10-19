# Lab 6

## 1. Objective

This lab helps students practice their skills and better their understanding of the topics of the lecture# 6:  String.

---

## 2. Tasks

### 2.1 Solve Tasks on Ejudge

Go to the ejudge system and solve the required problems.

🔗 **Lab problems**: [http://ejudge.kz/new-client?contest_id=6](http://ejudge.kz/new-client?contest_id=6)

📝 **Instructions**:
- Login with your credentials
- Solve and submit the assigned tasks
- Submit only `.cpp` files that compile and run without errors
---

## 3. What You Must Complete?

To pass this lab:

- ✅ Solve tasks successfully on [ejudge.kz](http://ejudge.kz/new-client?contest_id=6)

**Deadline**: check MS Teams announcements

---

## 4. 🛠 Troubleshooting

If you encounter issues:

- Revisit the lecture materials (github repo, lecture recording, etc.)
- Revisit the Compilation Guide
- Ask questions during the practice classes
- Bring your laptop to offline practice classes for live help

---

## 5. Quick Reference: String

This quick reference summarizes common operations with strings useful for lab tasks.

### Create / Initialize
- Default: `string s;`
- From literal: `string s = "hello";`
- From char array: `string s(charArray);`
- Repeat char: `string s(5, 'a');`

### Access & size
- Length / size: `s.size()` / `s.length()`
- Indexing: `s[i]` (no bounds check) or `s.at(i)` (throws out_of_range)
- Front / back: `s.front()`, `s.back()`
- Iterate: `for (char c : s) { ... }` or `for (auto it = s.begin(); it != s.end(); ++it)`

### Modify
- Append: `s += "more";` or `s.append("more");`
- Insert: `s.insert(pos, "text");`
- Erase: `s.erase(pos, len);` or `s.pop_back();`
- Replace: `s.replace(pos, len, "new");`
- Clear: `s.clear();`
- Resize: `s.resize(new_size);`

### Substrings & search
- Substring: `string sub = s.substr(pos, len);`
- Find: `s.find("pattern")` returns `npos` if not found

### Compare
- `s1 == s2`, `s1 != s2`, lexicographical `s1 < s2`

### Conversion
- String to int/double: `stoi(s)`, `stol(s)`, `stod(s)` (throws on invalid)
- Number to string: `to_string(n)`
- Use `stringstream` for complex parsing/formatting (`#include <sstream>`)

### I/O
- Read a word: `cin >> s;` (stops at whitespace)
- Read a full line: `getline(cin, s);`

### C-style strings
- Get C string: `s.c_str()` (null-terminated)

### Useful algorithms (with <algorithm>)
- Reverse: `reverse(s.begin(), s.end());`
- Sort characters: `sort(s.begin(), s.end());`
