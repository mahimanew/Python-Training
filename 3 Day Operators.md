
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
   
