
### **1. Introduction to Errors and Exceptions**

**Errors** can be classified into two types:
1. **Syntax Errors**: These occur when the Python interpreter cannot understand the code due to incorrect syntax (e.g., missing a colon or parentheses).
2. **Runtime Errors (Exceptions)**: These occur during the execution of the program, like trying to divide by zero or accessing an element out of range in a list.

---

### **2. What is Exception Handling?**

**Exception Handling** is the process of responding to exceptional conditions (run-time errors) in programs by using `try`, `except`, `else`, and `finally` blocks.

---

### **3. Basic Concept of Exception Handling**

#### **Try and Except Block**
The `try` block lets you test a block of code for errors. The `except` block lets you handle the error.

```python
try:
    num = int(input("Enter a number: "))
    result = 10 / num
    print(f"Result is: {result}")
except ZeroDivisionError:
    print("Cannot divide by zero!")
except ValueError:
    print("Invalid input! Please enter a number.")
```

In the above example:
- The program will ask for a number and attempt to divide 10 by that number.
- If the user enters `0`, the `ZeroDivisionError` will be caught.
- If the user enters anything other than a number, a `ValueError` will be caught.

---

### **4. Else Block**
The `else` block is executed if there is no exception raised in the `try` block.

```python
try:
    num = int(input("Enter a number: "))
    result = 10 / num
except ZeroDivisionError:
    print("Cannot divide by zero!")
except ValueError:
    print("Invalid input! Please enter a number.")
else:
    print(f"Result is: {result}")
```
Here, the `else` block executes only if there are no exceptions in the `try` block.

---

### **5. Finally Block**
The `finally` block is always executed, regardless of whether an exception occurred or not. This is typically used for cleanup actions like closing files or releasing resources.

```python
try:
    file = open("example.txt", "r")
    content = file.read()
    print(content)
except FileNotFoundError:
    print("File not found!")
finally:
    file.close()
    print("File closed.")
```

---

### **6. Raising Exceptions**
You can explicitly raise exceptions using the `raise` keyword. This is useful when you want to trigger an exception under certain conditions.

#### **Syntax:**
```python
raise Exception("Something went wrong!")
```

#### **Example:**
```python
def check_age(age):
    if age < 18:
        raise ValueError("Age must be 18 or older.")
    else:
        print("Age is valid.")

try:
    check_age(16)
except ValueError as e:
    print(e)  # Output: Age must be 18 or older.
```

---

### **7. Custom Exceptions**
You can create your own exceptions by defining a custom exception class that inherits from Python's built-in `Exception` class.

#### **Example:**
```python
class NegativeAgeError(Exception):
    def __init__(self, message="Age cannot be negative"):
        self.message = message
        super().__init__(self.message)

def check_age(age):
    if age < 0:
        raise NegativeAgeError("Age cannot be negative.")
    else:
        print("Age is valid.")

try:
    check_age(-5)
except NegativeAgeError as e:
    print(e)  # Output: Age cannot be negative.
```

---

### **8. Multiple Exceptions**
You can handle multiple types of exceptions in a single `try-except` block by specifying multiple `except` clauses.

```python
try:
    num = int(input("Enter a number: "))
    result = 10 / num
except ZeroDivisionError:
    print("Cannot divide by zero!")
except ValueError:
    print("Invalid input! Please enter a number.")
except Exception as e:
    print(f"An unexpected error occurred: {e}")
```

This way, you can handle a variety of exceptions efficiently.

---

### **9. Catching All Exceptions**
If you want to catch all exceptions, you can use a generic `except` clause. However, it's better to specify the types of exceptions you want to catch.

```python
try:
    x = 10 / 0
except Exception as e:
    print(f"Error: {e}")  # Output: Error: division by zero
```

Note that using a generic `except` clause can hide unexpected errors, so use it carefully.

---

### **10. Assertions**
Assertions are used to test if a condition is true. If the condition is false, it raises an `AssertionError` with an optional message.

#### **Syntax:**
```python
assert condition, "Error message"
```

#### **Example:**
```python
age = 25
assert age >= 18, "Age must be 18 or older"
print("Age is valid.")
```

If the `age` is less than 18, an `AssertionError` will be raised.

---

### **11. Advanced Exception Handling Topics**

#### **11.1. Exception Hierarchy**
In Python, exceptions form a hierarchy. All exceptions inherit from the base class `Exception`. Specific exceptions (like `ValueError`, `FileNotFoundError`, etc.) inherit from `Exception`. You can catch exceptions using the parent class, but it's better to catch more specific exceptions.

```python
try:
    # some code
except ValueError:
    # handle ValueError
except Exception:
    # handle all other exceptions
```

#### **11.2. Handling Nested Exceptions**
You can use nested `try-except` blocks to handle exceptions inside another exception block.

```python
try:
    x = int(input("Enter a number: "))
    try:
        result = 10 / x
    except ZeroDivisionError:
        print("Cannot divide by zero!")
except ValueError:
    print("Invalid input!")
```

#### **11.3. `with` Statement and Exception Handling**
The `with` statement can also be used with exception handling. It's particularly useful when dealing with files or resources that need to be automatically cleaned up.

```python
try:
    with open("file.txt", "r") as file:
        content = file.read()
except FileNotFoundError:
    print("File not found!")
```

---

### **12. Exercises for Day 10:**

1. **Basic:**
   - Write a program to handle division by zero.
   - Write a program that handles invalid user input (non-integer input).

2. **Intermediate:**
   - Write a program that raises a `ValueError` if the user enters a number less than 18 for age.
   - Create a custom exception for invalid email format and raise it when the email format is incorrect.

3. **Advanced:**
   - Write a program that handles multiple exceptions (e.g., FileNotFoundError, ValueError, etc.) while reading and writing to a file.
   - Implement an assertion in a program that checks whether a user's age is within a valid range.

---
