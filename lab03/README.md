# Lab 3

## 1. Objective

This lab helps students practice their skills and better their understanding of the topics of the third lecture:  Numeric Systems, Bits and Bitwise Operators.

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
| Binary (base 2) | Uses digits 0 and 1. Important for bitwise operations and low-level data representation. | 13 = 1101 |
| Octal (base 8) | Uses digits 0–7. Useful historically and sometimes in permission bits. | 15 = 17 |
| Hexadecimal (base 16) | Uses 0–9 and A–F. Compact representation of binary; common in programming and memory dumps. | 255 = FF = 11111111 |

### Bits and Bitwise Operators (C/C++ style)

| Operator | Symbol | Description | Example (a = 10 (10102), b = 6 (01102)) |
|---:|:---:|---|---|
| AND | & | Bitwise AND: result bit is 1 if both bits are 1. | a & b = 1010 & 0110 = 0010 = 2 |
| OR | \| | Bitwise OR: result bit is 1 if at least one bit is 1. | a \| b = 1010 | 0110 = 1110 = 14 |
| XOR | ^ | Bitwise XOR: result bit is 1 if bits differ. | a ^ b = 1010 ^ 0110 = 1100 = 12 |
| NOT | ~ | Bitwise NOT: flips all bits (two's complement for signed). | ~a (for 8-bit) = ~00001010 = 11110101 = 245 (or -11 signed)
| Left shift | << | Shifts bits left, fills with 0: multiplies by 2 per shift (for unsigned). | a << 1: 1010 << 1 = 10100 = 20 |
| Right shift | >> | Shifts bits right: logical (fills with 0) vs arithmetic (preserves sign). | a >> 1: 1010 >> 1 = 0101 = 5 (logical)

Notes and common patterns:
- Setting a bit: x |= (1 << n) sets bit n.
- Clearing a bit: x &= ~(1 << n) clears bit n.
- Toggling a bit: x ^= (1 << n) flips bit n.
- Checking bit: (x >> n) & 1 returns bit n (0 or 1).
- Check if even: (x & 1) == 0 -> true if even.

#### Truth tables (bitwise / boolean view)

AND (a & b)

| a | b | a & b |
|---:|---:|---:|
| 0 | 0 | 0 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

OR (a | b)

| a | b | a \| b |
|---:|---:|---:|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 1 |

XOR (a ^ b)

| a | b | a ^ b |
|---:|---:|---:|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

NOT (~a) — unary (bit flip)

| a | ~a |
|---:|---:|
| 0 | 1 |
| 1 | 0 |

### 4-bit examples

Decimal / Binary / Hex (4-bit unsigned range 0..15):

| Dec | Binary | Hex |
|---:|:---:|:---:|
| 0  | 0000 | 0 |
| 1  | 0001 | 1 |
| 2  | 0010 | 2 |
| 3  | 0011 | 3 |
| 4  | 0100 | 4 |
| 5  | 0101 | 5 |
| 6  | 0110 | 6 |
| 7  | 0111 | 7 |
| 8  | 1000 | 8 |
| 9  | 1001 | 9 |
| 10 | 1010 | A |
| 11 | 1011 | B |
| 12 | 1100 | C |
| 13 | 1101 | D |
| 14 | 1110 | E |
| 15 | 1111 | F |

Bitwise examples with 4-bit values (show binary steps):

- Let x = 1101 (13), y = 0110 (6)
	- x & y = 1101 & 0110 = 0100 = 4
	- x | y = 1101 | 0110 = 1111 = 15
	- x ^ y = 1101 ^ 0110 = 1011 = 11
	- ~x (4-bit) = ~1101 = 0010 = 2  (note: in real programs ~ works on full machine width)

Shifts (4-bit visual examples, result may need more bits in practice):

- 0101 (5) << 1 -> 1010 (10)
- 0101 (5) >> 1 -> 0010 (2)  (logical shift)

### Conversions
- **From any system to decimal**: Multiply each digit by its base raised to position power.
- **From decimal to binary**: Divide by 2 repeatedly, read remainders in reverse.
- **From decimal to octal**: Divide by 8 repeatedly, read remainders in reverse.
- **From decimal to hex**: Divide by 16 repeatedly, read remainders in reverse.