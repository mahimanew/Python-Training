
## **1. Introduction to Conditional Statements**
Conditional statements are used to execute code based on specific conditions. Python provides the following conditional constructs:

- **`if` statement**
- **`if-else` statement**
- **`if-elif-else` ladder**
- **Nested `if` statements**
- **Short-hand conditional statements (Ternary operator)**

---

## **2. The `if` Statement**
The `if` statement executes a block of code if the condition is `True`.

**Syntax**:
```python
if condition:
    # Code to execute if condition is True
```

**Example**:
```python
age = 18
if age >= 18:
    print("You are eligible to vote.")
```

---

## **3. The `if-else` Statement**
The `if-else` statement provides an alternative block of code to execute if the condition is `False`.

**Syntax**:
```python
if condition:
    # Code to execute if condition is True
else:
    # Code to execute if condition is False
```

**Example**:
```python
age = 16
if age >= 18:
    print("You are eligible to vote.")
else:
    print("You are not eligible to vote.")
```

---

## **4. The `if-elif-else` Ladder**
The `if-elif-else` ladder is used when you have multiple conditions to evaluate.

**Syntax**:
```python
if condition1:
    # Code to execute if condition1 is True
elif condition2:
    # Code to execute if condition2 is True
else:
    # Code to execute if all conditions are False
```

**Example**:
```python
marks = 85

if marks >= 90:
    print("Grade: A")
elif marks >= 75:
    print("Grade: B")
elif marks >= 60:
    print("Grade: C")
else:
    print("Grade: F")
```

---

## **5. Nested `if` Statements**
You can place one `if` statement inside another to handle complex scenarios.

**Syntax**:
```python
if condition1:
    if condition2:
        # Code to execute if both condition1 and condition2 are True
```

**Example**:
```python
age = 20
has_voter_id = True

if age >= 18:
    if has_voter_id:
        print("You are eligible to vote.")
    else:
        print("You need a voter ID to vote.")
else:
    print("You are not eligible to vote.")
```

---

## **6. Short-Hand Conditional Statements (Ternary Operator)**
The ternary operator allows you to write `if-else` statements in a single line.

**Syntax**:
```python
value_if_true if condition else value_if_false
```

**Example**:
```python
age = 20
message = "Eligible to vote" if age >= 18 else "Not eligible to vote"
print(message)
```

---

## **7. Logical Operators in Conditional Statements**
You can combine multiple conditions using `and`, `or`, and `not`.

**Example**:
```python
age = 25
is_registered = True

if age >= 18 and is_registered:
    print("You are eligible to vote.")
else:
    print("You are not eligible to vote.")
```

---

## **8. Advanced Examples**

### **Example 1: Checking Leap Year**
```python
year = 2024
if year % 4 == 0:
    if year % 100 != 0 or year % 400 == 0:
        print(f"{year} is a leap year.")
    else:
        print(f"{year} is not a leap year.")
else:
    print(f"{year} is not a leap year.")
```

---

### **Example 2: Maximum of Three Numbers**
```python
a, b, c = 10, 20, 15

if a > b and a > c:
    print(f"{a} is the largest.")
elif b > c:
    print(f"{b} is the largest.")
else:
    print(f"{c} is the largest.")
```

---

### **Example 3: Login System**
```python
username = "admin"
password = "12345"

input_username = input("Enter username: ")
input_password = input("Enter password: ")

if input_username == username and input_password == password:
    print("Login successful!")
else:
    print("Invalid credentials.")
```

---

## **9. Common Errors in Conditional Statements**
1. **Indentation Errors**:
   - Python uses indentation to define blocks. Improper indentation causes errors.
   ```python
   if True:
   print("Hello")  # This will raise an IndentationError
   ```

2. **Improper Logical Operators**:
   - Avoid using `and`/`or` improperly with multiple conditions.
   ```python
   if a > 0 or b < 0 and c == 5:  # Use parentheses for clarity
   ```

3. **Misusing Assignment (`=`) Instead of Comparison (`==`)**:
   ```python
   if a = 10:  # Incorrect
   if a == 10:  # Correct
   ```

---

## **10. Exercises**
1. Write a program to check if a given number is positive, negative, or zero.
2. Write a program to determine the grade based on marks (use `if-elif-else`).
3. Write a program to check whether a given year is a leap year.
4. Write a program to check if a person is eligible for a driver's license (age >= 18 and eyesight test passed).
5. Write a program to find the largest of three numbers using nested `if`.

---

## **11. Real-World Applications**
- **Decision-Making**: Determine actions based on user input or external conditions.
- **Data Validation**: Check if user inputs meet specific criteria.
- **Flow Control**: Use conditional statements to guide the flow of a program.

---
