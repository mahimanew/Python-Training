

### **1. Introduction to Functions**
**Basic Concept:**
A function is a block of code that only runs when it is called. It can accept parameters and return a value.
- Functions help break down complex problems into smaller, manageable tasks.

#### **Syntax:**
```python
def function_name(parameters):
    # function body
    return value
```

#### **Example:**
```python
def greet():
    print("Hello, Welcome to Python!")

greet()  # Output: Hello, Welcome to Python!
```

---

### **2. Function Parameters**
**Basic Concept:**
Functions can accept parameters (or arguments) to operate on.

#### **Positional Arguments:**
Arguments are passed in the same order they are defined in the function.
```python
def add(x, y):
    return x + y

print(add(5, 3))  # Output: 8
```

#### **Default Arguments:**
You can set default values for parameters.
```python
def greet(name="Guest"):
    print(f"Hello, {name}!")

greet()  # Output: Hello, Guest!
greet("Alice")  # Output: Hello, Alice!
```

#### **Keyword Arguments:**
You can pass arguments by explicitly specifying their names.
```python
def greet(name, age):
    print(f"Hello {name}, you are {age} years old!")

greet(name="Alice", age=25)  # Output: Hello Alice, you are 25 years old!
```

#### **Arbitrary Arguments (`*args`):**
Allows passing a variable number of non-keyword arguments.
```python
def print_numbers(*args):
    for num in args:
        print(num)

print_numbers(1, 2, 3, 4)  # Output: 1 2 3 4
```

#### **Arbitrary Keyword Arguments (`**kwargs`):**
Allows passing a variable number of keyword arguments.
```python
def print_info(**kwargs):
    for key, value in kwargs.items():
        print(f"{key}: {value}")

print_info(name="Alice", age=25)  
# Output: name: Alice
#         age: 25
```

---

### **3. Returning Values from Functions**
Functions can return values using the `return` keyword.

#### **Example:**
```python
def multiply(x, y):
    return x * y

result = multiply(5, 3)
print(result)  # Output: 15
```

#### **Returning Multiple Values:**
You can return multiple values as a tuple.
```python
def math_operations(a, b):
    return a + b, a - b, a * b, a / b

result = math_operations(10, 5)
print(result)  # Output: (15, 5, 50, 2.0)
```

---

### **4. Advanced Topics**
---

#### **4.1. Recursion**
Recursion is when a function calls itself to solve smaller sub-problems.

##### **Example:**
Calculating the factorial of a number.
```python
def factorial(n):
    if n == 0:
        return 1
    else:
        return n * factorial(n-1)

print(factorial(5))  # Output: 120
```

##### **Example Explanation:**
- `factorial(5)` calls `factorial(4)`, `factorial(4)` calls `factorial(3)`, and so on, until `factorial(0)` returns 1.
- This is a classic example of **divide and conquer**.

#### **4.2. Variable Scope**
The scope of a variable defines where in the program a variable can be accessed. It can either be local or global.

**Local Scope:**
A variable defined inside a function is local to that function.

```python
def my_function():
    x = 10  # x is local to my_function
    print(x)

my_function()  # Output: 10
```

**Global Scope:**
A variable defined outside any function is global and can be accessed inside functions (using `global` keyword).

```python
x = 10  # Global variable

def my_function():
    global x
    x = 20  # Modifies global x
    print(x)

my_function()  # Output: 20
print(x)  # Output: 20 (global x is updated)
```




---

#### **4.3. Lambda Functions**
A lambda function is an anonymous function defined using the `lambda` keyword.

##### **Syntax:**
```python
lambda arguments: expression
```

##### **Example:**
```python
square = lambda x: x**2
print(square(5))  # Output: 25
```

##### **Example with `map()`**:
```python
nums = [1, 2, 3, 4]
squared_nums = list(map(lambda x: x**2, nums))
print(squared_nums)  # Output: [1, 4, 9, 16]
```

---

#### **4.4. Nested Functions**
A function inside another function can access variables from the outer function. This is often used in closures.

```python
def outer():
    x = 10
    def inner():
        print(x)
    inner()

outer()  # Output: 10
```

---

### **5. Advanced Function Concepts**
---

#### **5.1. Decorators**
A decorator is a function that takes another function and extends its behavior without explicitly modifying it.

##### **Syntax:**
```python
def decorator(func):
    def wrapper():
        print("Before the function call")
        func()
        print("After the function call")
    return wrapper

@decorator
def say_hello():
    print("Hello!")

say_hello()
# Output:
# Before the function call
# Hello!
# After the function call
```

Decorators are widely used in frameworks like Flask and Django for routing, middleware, etc.

---



---

### **Exercises for Day 8:**

1. **Basic:**
   - Write a function that takes two numbers and returns their sum.
   - Write a function to calculate the area of a rectangle using default arguments for length and width.

2. **Intermediate:**
   - Write a function that checks if a number is prime (using recursion).
   - Write a program that returns the nth Fibonacci number using recursion.
   - Create a function that takes a tuple of numbers and returns a new tuple with the squares of each number.

3. **Advanced:**
   - Write a decorator that logs the function call with arguments and return values.
   - Create a closure that counts how many times a function is called.

---

