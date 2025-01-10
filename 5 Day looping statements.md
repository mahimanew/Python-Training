
## **1. Introduction to Loops**
Loops are used to execute a block of code repeatedly as long as a condition is met. Python provides two types of loops:
- **`for` loop**
- **`while` loop**

---

## **2. The `for` Loop**
The `for` loop iterates over a sequence (e.g., list, tuple, string, range).

### **Basic Syntax**:
```python
for variable in sequence:
    # Code to execute for each item in the sequence
```

### **Examples**:
1. **Iterating over a list**:
   ```python
   fruits = ["apple", "banana", "cherry"]
   for fruit in fruits:
       print(fruit)
   ```

2. **Using `range()`**:
   ```python
   for i in range(5):  # Iterates from 0 to 4
       print(i)
   ```

3. **Iterating over a string**:
   ```python
   for char in "Python":
       print(char)
   ```

---

## **3. The `while` Loop**
The `while` loop executes as long as the condition is `True`.

### **Basic Syntax**:
```python
while condition:
    # Code to execute while condition is True
```

### **Examples**:
1. **Basic Example**:
   ```python
   x = 5
   while x > 0:
       print(x)
       x -= 1
   ```

2. **User Input Example**:
   ```python
   password = ""
   while password != "1234":
       password = input("Enter password: ")
   print("Access granted!")
   ```

---

## **4. Control Statements**
Control statements alter the flow of loops.

### **`break` Statement**:
Used to exit a loop prematurely.
```python
for i in range(10):
    if i == 5:
        break
    print(i)
```

### **`continue` Statement**:
Skips the current iteration and proceeds to the next.
```python
for i in range(10):
    if i % 2 == 0:
        continue
    print(i)
```

### **`pass` Statement**:
A placeholder that does nothing. Useful for future implementation.
```python
for i in range(5):
    if i == 3:
        pass
    else:
        print(i)
```

---

## **5. Nested Loops**
A loop inside another loop.

### **Example**:
```python
for i in range(3):
    for j in range(2):
        print(f"i: {i}, j: {j}")
```

---

## **6. Loop with `else` Clause**
The `else` clause in loops is executed when the loop is completed without a `break`.

### **Example**:
1. **For loop with `else`**:
   ```python
   for i in range(5):
       print(i)
   else:
       print("Loop finished!")
   ```

2. **While loop with `else`**:
   ```python
   x = 0
   while x < 3:
       print(x)
       x += 1
   else:
       print("Loop completed!")
   ```

---

## **7. Advanced Concepts**

### **Using `enumerate()` in Loops**
Used to get both index and value when iterating.
```python
names = ["Alice", "Bob", "Charlie"]
for index, name in enumerate(names):
    print(f"Index: {index}, Name: {name}")
```

### **Using `zip()` in Loops**
Used to iterate over two or more sequences simultaneously.
```python
names = ["Alice", "Bob", "Charlie"]
ages = [25, 30, 35]
for name, age in zip(names, ages):
    print(f"{name} is {age} years old.")
```

### **Iterating Backwards**
Using `reversed()`:
```python
for i in reversed(range(5)):
    print(i)
```

### **Looping with a Step**
Using `range()` with a step value:
```python
for i in range(0, 10, 2):
    print(i)  # Outputs: 0, 2, 4, 6, 8
```

---

## **8. Common Errors in Loops**
1. **Infinite Loops**:
   Occur when the condition in a `while` loop never becomes `False`.
   ```python
   x = 5
   while x > 0:
       print(x)  # Infinite loop
   ```

2. **Improper Range**:
   Forgetting the correct range boundaries.
   ```python
   for i in range(1, 10):  # Stops at 9, not 10
   ```

---

## **9. Exercises**

### **Basic**:
1. Write a program to print numbers from 1 to 10 using both `for` and `while` loops.
2. Iterate over a list of colors (`["red", "blue", "green"]`) and print each color.
3. Print the multiplication table of a given number.

### **Intermediate**:
4. Write a program to count the number of vowels in a string using a loop.
5. Print all numbers from 1 to 50 that are divisible by 3 and 5.
6. Create a nested loop to print a pattern:
   ```
   *
   **
   ***
   ****
   *****
   ```

### **Advanced**:
7. Write a program to check if a number is prime.
8. Iterate over two lists simultaneously using `zip()` and print their sum.
9. Create a program to calculate the factorial of a number using a loop.
10. Write a program to check if a given string is a palindrome using loops.

---

## **10. Real-World Applications**
1. **Data Processing**: Loops are used to iterate through datasets or perform repetitive tasks like file operations.
2. **Simulations**: Nested loops can simulate grids, such as in games or scientific calculations.
3. **Automation**: Automating repetitive tasks like sending multiple emails.

---


---

## **1. Understanding `do-while` Behavior**
A `do-while` loop ensures that the block of code executes at least once, regardless of whether the condition is `True` or `False`.

**Note:** Python does not have a built-in `do-while` loop like some other programming languages (e.g., C, C++, Java). However, you can mimic the behavior of a `do-while` loop in Python using a combination of a `while` loop and an initial block of code executed before the condition is checked.


**In languages with `do-while`, the syntax looks like this:**
```c
do {
    // Code block
} while (condition);
```

In Python, we simulate this behavior because Python doesn't support it directly.

---

## **2. Mimicking `do-while` in Python**
We can achieve this using a `while` loop with an initial execution of the code block.

### **Basic Syntax**:
```python
while True:
    # Code block
    if not condition:
        break
```

---

## **3. Examples of Simulated `do-while` in Python**

### **Example 1: User Input Validation**
```python
while True:
    number = int(input("Enter a positive number: "))
    if number > 0:
        print("Thank you!")
        break
    else:
        print("The number must be positive. Try again.")
```

### **Example 2: Password Authentication**
```python
correct_password = "python123"

while True:
    password = input("Enter your password: ")
    if password == correct_password:
        print("Access granted!")
        break
    else:
        print("Incorrect password. Try again.")
```

### **Example 3: Menu-Driven Program**
```python
while True:
    print("1. Option 1")
    print("2. Option 2")
    print("3. Exit")
    choice = int(input("Enter your choice: "))
    
    if choice == 1:
        print("You selected Option 1")
    elif choice == 2:
        print("You selected Option 2")
    elif choice == 3:
        print("Exiting program...")
        break
    else:
        print("Invalid choice. Try again.")
```

---

## **4. How It Differs from `while`**
The key difference between a regular `while` loop and a simulated `do-while` loop is that the code block executes at least once before the condition is checked.

---

## **5. Exercises**

### **Basic**:
1. Write a program that asks the user to guess a secret number. The loop should run until the correct number is guessed.

### **Intermediate**:
2. Create a program that repeatedly asks for a user's name until a non-empty string is entered.

### **Advanced**:
3. Simulate a simple calculator where the user can perform addition, subtraction, multiplication, or division. The loop should continue until the user chooses to exit.

