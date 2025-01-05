

### **1. Introduction to Python**
- **Concepts**: 
  - What is Python?
  - Python as an interpreted, high-level, and versatile programming language.
  - Setting up Python (install Python and an IDE like VS Code, PyCharm, or Jupyter Notebook).

- **Example**:
  ```python
  print("Welcome to Python Programming!")
  ```

- **Questions**:
  - What are the key features of Python?
  - Write a Python program to print your name.

---

### **2. Variables and Data Types**
- **Concepts**:
  - Variables: Names that store data.
  - Data types: Integers, floats, strings, booleans.

- **Example**:
  ```python
  name = "John"
  age = 18
  is_student = True
  print(f"Name: {name}, Age: {age}, Student: {is_student}")
  ```

- **Questions**:
  - Create a variable to store your favorite color.
  - What is the output of the following code?
    ```python
    x = 10
    y = 5
    print(x + y)
    ```

---

### **3. Input and Output**
- **Concepts**:
  - Taking user input.
  - Formatting output.

- **Example**:
  ```python
  name = input("Enter your name: ")
  print(f"Hello, {name}!")
  ```

- **Questions**:
  - Write a program to take your age as input and print "You are [age] years old".
  - What will happen if you enter a number instead of text as input in the example?

---

### **4. Control Structures**
- **Concepts**:
  - If-else statements.
  - Loops (for and while).

- **Example**:
  ```python
  # If-else
  num = int(input("Enter a number: "))
  if num % 2 == 0:
      print("Even")
  else:
      print("Odd")
  
  # Loop
  for i in range(1, 6):
      print(i)
  ```

- **Questions**:
  - Write a program to check if a number is positive, negative, or zero.
  - Write a loop to print the first 10 multiples of 5.

---

### **5. Functions**
- **Concepts**:
  - What are functions?
  - Defining and calling functions.

- **Example**:
  ```python
  def greet(name):
      print(f"Hello, {name}!")
  
  greet("Alice")
  ```

- **Questions**:
  - Write a function that takes two numbers and returns their sum.
  - Why are functions useful in programming?

---

### **6. Lists and Loops**
- **Concepts**:
  - Lists: Collection of items.
  - Looping through lists.

- **Example**:
  ```python
  fruits = ["apple", "banana", "cherry"]
  for fruit in fruits:
      print(f"I like {fruit}")
  ```

- **Questions**:
  - Create a list of your top 3 favorite movies.
  - Write a program to find the largest number in a list.

---

### **7. Basic Error Handling**
- **Concepts**:
  - Try-except blocks to handle errors.

- **Example**:
  ```python
  try:
      num = int(input("Enter a number: "))
      print(f"Square of {num} is {num**2}")
  except ValueError:
      print("That's not a valid number!")
  ```

- **Questions**:
  - Why is error handling important?
  - Modify the example to handle division by zero.

---

### **8. Basic File Handling**
- **Concepts**:
  - Reading from and writing to files.

- **Example**:
  ```python
  with open("example.txt", "w") as file:
      file.write("Hello, file!")
  
  with open("example.txt", "r") as file:
      content = file.read()
      print(content)
  ```

- **Questions**:
  - Write a program to write your name and age into a file.
  - How do you handle errors while working with files?

---

