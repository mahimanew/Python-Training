### **1. What are Variables?**
- **Concept**:
  - Variables are names that store data values.
  - A variable is created the moment a value is assigned to it.
  
- **Syntax**:
  ```python
  variable_name = value
  ```

- **Example**:
  ```python
  age = 18
  name = "Alice"
  is_student = True
  type(age)
  type(name)
  type(is_student)

  ```

- **Exercise**:
  - Create variables to store your name, age, and favorite hobby, then print them.

---

### **2. Basic Data Types**
- **Concept**:
  - Common data types in Python:
    - `int` (integer): Numbers without decimals.
    - `float`: Numbers with decimals.
    - `str` (string): Text enclosed in quotes.
    - `bool` (boolean): True or False values.

- **Example**:
  ```python
  price = 19.99  # float
  count = 10     # int
  message = "Hello, Python!"  # str
  is_available = True  # bool
  ```

- **Exercise**:
  - Write a program to create variables for a product name, price, and availability, then print them.

---

### **3. Dynamic Typing**
- **Concept**:
  - Python is dynamically typed; variables can change types during execution.

- **Example**:
  ```python
  x = 10      # int
  x = "Ten"   # str
  print(x)
  ```

- **Exercise**:
  - Assign different data types to a single variable and observe the behavior.

---

### **4. Multiple Assignments**
- **Concept**:
  - Python allows assigning values to multiple variables in a single line.

- **Example**:
  ```python
  a, b, c = 1, 2.5, "Python"
  print(a, b, c)
  ```

- **Exercise**:
  - Assign your name, age, and city to three variables in one line.

---

### **5. Type Casting**
- **Concept**:
  - Converting one data type to another using functions like `int()`, `float()`, `str()`, etc.

- **Example**:
  ```python
  age = "18"  # str
  age = int(age)  # Convert to int
  print(age + 2)  # Output: 20
  ```

- **Exercise**:
  - Take a string input from the user, convert it to a number, and add 10 to it.

---

### **6. Strings**
- **Concept**:
  - Strings are sequences of characters.
  - Strings can use single or double quotes.
  - Strings are immutable.

- **Example**:
  ```python
  greeting = "Hello"
  print(greeting[0])  # Access first character
  print(len(greeting))  # Length of string
  ```

- **Exercise**:
  - Write a program to take your name as input and print its length.

---

### **7. Lists and Tuples**
- **Concept**:
  - **List**: Ordered, mutable collection.
  - **Tuple**: Ordered, immutable collection.

- **Example**:
  ```python
  fruits = ["apple", "banana", "cherry"]  # List
  colors = ("red", "green", "blue")      # Tuple
  print(fruits[1])  # banana
  print(colors[-1])  # blue
  type(fruits)
  type(colors)


  ```

- **Exercise**:
  - Create a list of 3 favorite foods and a tuple of 3 favorite colors. Print the second item in each.

---

### **8. Dictionaries**
- **Concept**:
  - Key-value pairs, mutable, unordered.

- **Example**:
  ```python
  student = {"name": "Alice", "age": 18, "grade": "A"}
  print(student["name"])  # Alice
  type(student)

  ```

- **Exercise**:
  - Create a dictionary with your name, age, and favorite hobby, then print each value.

---

### **9. Advanced Concepts**
#### a. **Mutable vs Immutable Types**
- **Concept**:
  - Mutable: Can be changed (e.g., lists, dictionaries).
  - Immutable: Cannot be changed (e.g., strings, tuples).

- **Example**:
  ```python
  # Mutable
  numbers = [1, 2, 3]
  numbers[0] = 10
  print(numbers)  # [10, 2, 3]

  # Immutable
  name = "Alice"
  # name[0] = "B"  # Error
  ```

#### b. **Type Annotations** (Optional)
- **Concept**:
  - Indicating variable types for clarity.
  
- **Example**:
  ```python
  age: int = 18
  name: str = "Alice"
  ```

#### c. **Global and Local Variables**
- **Concept**:
  - Global variables are accessible throughout the program.
  - Local variables exist only within a function.

- **Example**:
  ```python
  x = 10  # Global

  def show():
      y = 20  # Local
      print(x + y)
  show()
  ```

- **Exercise**:
  - Create a program with a global variable and modify it inside a function.

---

### **10. Advanced Exercises**
1. Create a program that accepts a user’s name, age, and favorite hobby and stores them in a dictionary.
2. Write a program to calculate the average of numbers stored in a list.
3. Create a function that takes a tuple of numbers and returns a new tuple with the squares of each number.
4. Explain what happens when you try to modify a tuple or a string.

---


---
## Run time values
### **1. Integer (`int`)**
- **Code**:
  ```python
  age = int(input("Enter your age (integer): "))
  print("Your age is:", age)
  ```

- **Explanation**:
  - The `input()` function always returns a string.
  - Use `int()` to convert the string input to an integer.

---

### **2. Float (`float`)**
- **Code**:
  ```python
  price = float(input("Enter the price (float): "))
  print("The price is:", price)
  ```

- **Explanation**:
  - Use `float()` to convert the input string to a floating-point number.

---

### **3. String (`str`)**
- **Code**:
  ```python
  name = input("Enter your name (string): ")
  print("Hello,", name)
  ```

- **Explanation**:
  - No conversion is needed since `input()` returns a string by default.

---

### **4. Boolean (`bool`)**
- **Code**:
  ```python
  is_admin = input("Are you an admin? (True/False): ").strip().capitalize() == "True"
if is_admin:
    print("Welcome, Admin!")
else:
    print("You do not have admin privileges.")

  ```

- **Explanation**:
  - Compare the input string with `"yes"` to determine the boolean value.

---

### **5. List**
- **Code**:
  ```python
  numbers = input("Enter numbers separated by commas: ").split(",")
  numbers = [int(num.strip()) for num in numbers]  # Convert to integers
  print("List of numbers:", numbers)
type(numbers)

  ```

- **Explanation**:
  - Use `.split()` to split the input into a list of strings.
  - Convert each string to the desired data type (e.g., `int`).

---

### **6. Tuple**
- **Code**:
  ```python
  values = input("Enter values separated by commas: ").split(",")
  values = tuple(value.strip() for value in values)
  print("Tuple of values:", values)
  ```

- **Explanation**:
  - Use `.split()` to create a list and then convert it to a tuple.

---

### **7. Dictionary**
- **Code**:
  ```python
  keys = input("Enter keys separated by commas: ").split(",")
  values = input("Enter values separated by commas: ").split(",")
  data = dict(zip(keys, values))
  print("Dictionary:", data)
  ```

- **Explanation**:
  - Use `zip()` to combine keys and values into a dictionary.

---

### **8. Advanced Example: Mixed Data Types**
If you want to input multiple data types in a single run:
- **Code**:
  ```python
  name = input("Enter your name: ")  # str
  age = int(input("Enter your age: "))  # int
  height = float(input("Enter your height in meters: "))  # float
  is_student = input("Are you a student? (yes/no): ").lower() == "yes"  # bool

  print(f"Name: {name}, Age: {age}, Height: {height}, Student: {is_student}")
  ```

---

### **Error Handling for Runtime Inputs**
It’s important to handle invalid inputs gracefully.

- **Code**:
  ```python
  try:
      age = int(input("Enter your age: "))
      print("Your age is:", age)
  except ValueError:
      print("Invalid input! Please enter a valid integer.")
  ```

---

### **Exercises**
1. Write a program to input three numbers from the user and print their average.
2. Create a program to take a list of favorite foods from the user and display them as a tuple.
3. Accept a dictionary input where the user enters keys and values as a single string (e.g., "name:John, age:25") and parse it into a dictionary.


