
### **1. Introduction to Operators**
Operators are symbols or keywords used to perform operations on variables and values. Python provides various types of operators:

- **Arithmetic Operators**
- **Relational (Comparison) Operators**
- **Logical Operators**
- **Assignment Operators**
- **Identity Operators**
- **Membership Operators**

---

### **2. Arithmetic Operators (Basic)**
Used for mathematical operations.

| Operator | Description          | Example           |
|----------|----------------------|-------------------|
| `+`      | Addition             | `5 + 3 = 8`       |
| `-`      | Subtraction          | `5 - 3 = 2`       |
| `*`      | Multiplication       | `5 * 3 = 15`      |
| `/`      | Division             | `5 / 2 = 2.5`     |
| `//`     | Floor Division       | `5 // 2 = 2`      |
| `%`      | Modulus (remainder)  | `5 % 2 = 1`       |
| `**`     | Exponentiation       | `2 ** 3 = 8`      |

- **Example**:
  ```python
  a = 10
  b = 3
  print(a + b)  # Addition
  print(a - b)  # Subtraction
  print(a * b)  # Multiplication
  print(a / b)  # Division
  print(a // b) # Floor Division
  print(a % b)  # Modulus
  print(a ** b) # Exponentiation
  ```

---

### **3. Relational (Comparison) Operators**
Used to compare two values and return a boolean (`True` or `False`).

| Operator | Description       | Example       |
|----------|-------------------|---------------|
| `==`     | Equal to          | `5 == 3` → `False` |
| `!=`     | Not equal to      | `5 != 3` → `True`  |
| `>`      | Greater than      | `5 > 3` → `True`   |
| `<`      | Less than         | `5 < 3` → `False`  |
| `>=`     | Greater or equal  | `5 >= 3` → `True`  |
| `<=`     | Less or equal     | `5 <= 3` → `False` |

- **Example**:
  ```python
  x = 10
  y = 5
  print(x == y)  # False
  print(x != y)  # True
  print(x > y)   # True
  print(x < y)   # False
  print(x >= y)  # True
  print(x <= y)  # False
  ```

---

### **4. Logical Operators**
Used to combine conditional statements.

| Operator | Description                 | Example                      |
|----------|-----------------------------|------------------------------|
| `and`    | True if both conditions are true | `(5 > 3 and 3 < 8)` → `True` |
| `or`     | True if at least one condition is true | `(5 > 3 or 3 > 8)` → `True` |
| `not`    | Reverses the condition      | `not(5 > 3)` → `False`       |

- **Example**:
  ```python
  a = 5
  b = 10
  print(a > 3 and b < 15)  # True
  print(a > 3 or b > 15)   # True
  print(not(a > 3))        # False
  ```

---

### **5. Assignment Operators**
Used to assign values to variables with shorthand for arithmetic operations.

| Operator | Description        | Example       |
|----------|--------------------|---------------|
| `=`      | Assign value       | `x = 5`       |
| `+=`     | Add and assign     | `x += 3` → `x = x + 3` |
| `-=`     | Subtract and assign| `x -= 3` → `x = x - 3` |
| `*=`     | Multiply and assign| `x *= 3` → `x = x * 3` |
| `/=`     | Divide and assign  | `x /= 3` → `x = x / 3` |
| `%=`     | Modulus and assign | `x %= 3` → `x = x % 3` |
| `//=`    | Floor divide and assign | `x //= 3`  |
| `**=`    | Exponent and assign| `x **= 3`     |

- **Example**:
  ```python
  x = 10
  x += 5  # Equivalent to x = x + 5
  print(x)  # Output: 15
  x //= 3  # Equivalent to x = x // 3
  print(x)  # Output: 5
  ```

---

### **6. Identity Operators**
Used to check if two objects are the same object (memory location).

| Operator | Description                  | Example              |
|----------|------------------------------|----------------------|
| `is`     | True if objects are the same | `x is y`            |
| `is not` | True if objects are different| `x is not y`        |

- **Example**:
  ```python
  a = [1, 2, 3]
  b = a
  c = [1, 2, 3]

  print(a is b)       # True (same object)
  print(a is c)       # False (different objects)
  print(a is not c)   # True
  ```

---

### **7. Membership Operators**
Used to check if a value is present in a sequence (e.g., list, tuple, string).

| Operator | Description                      | Example       |
|----------|----------------------------------|---------------|
| `in`     | True if value is in the sequence | `x in y`      |
| `not in` | True if value is not in sequence | `x not in y`  |

- **Example1**:
  ```python
  my_list = [1, 2, 3, 4]
  print(2 in my_list)       # True
  print(5 not in my_list)   # True
  ```

- **Example 2**
  ```
  # Define a variable
x = 42

# Get the memory address
address = id(x)

# Print the address in decimal and hexadecimal
print(f"Address of x in decimal: {address}")
print(f"Address of x in hexadecimal: {hex(address)}")
```
  

---


### **9. Exercises**
1. Write a program to calculate the result of an arithmetic expression using user inputs.
2. Check if a given number is both positive and even using logical operators.
3. Write a program to check if a string contains the letter "a" using membership operators.
4. Compare two lists to check if they are the same object or just have the same values.
5. Perform bitwise operations on two numbers input by the user.

---

### **10. Practical Applications**
1. **Arithmetic Operators**: Used in calculators or mathematical models.
2. **Logical Operators**: Used in decision-making (e.g., form validations).
3. **Membership Operators**: Searching in lists or strings.

- **Bonus**
Binary (Byte)	Decimal	Octal	Hexadecimal
00000000	0	0	0x00
00000001	1	1	0x01
00000010	2	2	0x02
00000011	3	3	0x03
00000100	4	4	0x04
00000101	5	5	0x05
00000110	6	6	0x06
00000111	7	7	0x07
00001000	8	10	0x08
00001001	9	11	0x09
00001010	10	12	0x0A
00001011	11	13	0x0B
00001100	12	14	0x0C
00001101	13	15	0x0D
00001110	14	16	0x0E
00001111	15	17	0x0F
00010000	16	20	0x10
00010001	17	21	0x11
00010010	18	22	0x12
00010011	19	23	0x13
00010100	20	24	0x14
00010101	21	25	0x15
00010110	22	26	0x16
00010111	23	27	0x17
00011000	24	30	0x18
00011001	25	31	0x19
00011010	26	32	0x1A
00011011	27	33	0x1B
00011100	28	34	0x1C
00011101	29	35	0x1D
00011110	30	36	0x1E
00011111	31	37	0x1F
00100000	32	40	0x20
00111111	63	77	0x3F
01000000	64	100	0x40
01111111	127	177	0x7F
10000000	128	200	0x80
11111111	255	377	0xFF


1. Binary (8421 System)
2. Octal (421 System)
3. Hexadecimal (8421 x 2 System)


Summary of Place Value Shortcuts:
Base	Shortcut	Place Values
Binary	8421	
2
3
=
8
,
2
2
=
4
,
2
1
=
2
,
2
0
=
1
2 
3
 =8,2 
2
 =4,2 
1
 =2,2 
0
 =1
Octal	421	
8
2
=
64
,
8
1
=
8
,
8
0
=
1
8 
2
 =64,8 
1
 =8,8 
0
 =1
Hexadecimal	8421 x 2	
1
6
1
=
16
,
1
6
0
=
1
16 
1
 =16,16 
0
 =1
