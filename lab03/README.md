# Lab 3

## 1. Objective

This lab helps students practice their skills and better their understanding of the topics of the second lecture:  Numeric Systems, Bits and Bitwise Operators.

---

## 2. Tasks

### 2.1 Solve Tasks on Ejudge

Go to the ejudge system and solve the required problems.

🔗 **Lab 3**: [http://ejudge.kz/new-client?contest_id=3](http://ejudge.kz/new-client?contest_id=3)

📝 **Instructions**:
- Login with your credentials
- Solve and submit the assigned tasks
- Submit only `.cpp` files that compile and run without errors
---

## 3. What You Must Complete?

To pass this lab:

- ✅ Solve tasks successfully on [ejudge.kz](http://ejudge.kz/new-client?contest_id=3)

**Deadline**: check MS Teams announcements

---

## 4. 🛠 Troubleshooting

If you encounter issues:

- Revisit the lecture materials (github repo, lecture recording, etc.)
- Revisit the Compilation Guide
- Ask questions during the practice classes
- Bring your laptop to offline practice classes for live help

---

## 5. Quick Reference: Numeric Systems & Bitwise Operators

Below are compact helper tables and short examples meant to help you during exercises and while solving problems on ejudge.

### Numeric Systems

| Concept | Description | Example |
|---|---:|---|
| Binary (base 2) | Uses digits 0 and 1. Important for bitwise operations and low-level data representation. | 1310 = 11012 |
| Octal (base 8) | Uses digits 0–7. Useful historically and sometimes in permission bits. | 158 = 1710 |
| Decimal (base 10) | Standard human-readable numbering. | 4210 = 42 |
| Hexadecimal (base 16) | Uses 0–9 and A–F. Compact representation of binary; common in programming and memory dumps. | 25510 = FF16 = 111111112 |
| Conversion tips | Divide by new base, read remainders bottom-up; or group binary digits (3 bits -> octal, 4 bits -> hex). | 1) 1101112 -> group 4: 0011 0111 -> 3 7 -> 3716? (binary->hex process)

Short conversions:

- Binary -> Hex: group bits into 4 from right: 11010110 -> (1101)(0110) -> D6
- Binary -> Octal: group bits into 3 from right: 101110 -> (101)(110) -> 5 6 -> 56

### Bits and Bitwise Operators (C/C++ style)

| Operator | Symbol | Description | Example (a = 10 (10102), b = 6 (01102)) |
|---:|:---:|---|---|
| AND | & | Bitwise AND: result bit is 1 if both bits are 1. | a & b = 1010 & 0110 = 0010 = 2 |
| OR | | | Bitwise OR: result bit is 1 if at least one bit is 1. | a | b = 1010 | 0110 = 1110 = 14 |
| XOR | ^ | Bitwise XOR: result bit is 1 if bits differ. | a ^ b = 1010 ^ 0110 = 1100 = 12 |
| NOT | ~ | Bitwise NOT: flips all bits (two's complement for signed). | ~a (for 8-bit) = ~00001010 = 11110101 = 245 (or -11 signed)
| Left shift | << | Shifts bits left, fills with 0: multiplies by 2 per shift (for unsigned). | a << 1: 1010 << 1 = 10100 = 20 |
| Right shift | >> | Shifts bits right: logical (fills with 0) vs arithmetic (preserves sign). | a >> 1: 1010 >> 1 = 0101 = 5 (logical)

Notes and common patterns:

- Masking: use & with a mask to extract bits. Example: x & 1 extracts LSB.
- Setting a bit: x |= (1 << n) sets bit n.
- Clearing a bit: x &= ~(1 << n) clears bit n.
- Toggling a bit: x ^= (1 << n) flips bit n.
- Checking bit: (x >> n) & 1 returns bit n (0 or 1).

Small examples:

- Check if even: (x & 1) == 0 -> true if even.
- Isolate lowest set bit: x & -x (two's complement) -> only lowest 1 remains.

Recommended quick exercises for practice:
1. Convert 20210 to binary and hex.
2. Compute (29 & 15), (29 | 15), (29 ^ 15) and show binary steps.
3. Given x = 0, set bits 0, 3, and 5 using shifts and ORs; show final value in decimal and binary.