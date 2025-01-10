
## **1. Introduction**
Lists, Tuples, and Dictionaries are core data structures in Python used to store and manipulate collections of data.

---

## **2. Lists**
A list is a mutable (changeable) sequence of elements, which can be of mixed data types.

### **Basic Concepts**

#### **Creating a List**
```python
# A list of integers
numbers = [1, 2, 3, 4]

# A mixed-type list
mixed = [1, "hello", 3.14]
```

#### **Accessing Elements**
```python
fruits = ["apple", "banana", "cherry"]

print(fruits[0])  # Output: apple
print(fruits[-1])  # Output: cherry
```

#### **Modifying Lists**
```python
fruits[1] = "blueberry"  # Modify an element
print(fruits)  # Output: ['apple', 'blueberry', 'cherry']
```

#### **List Operations**
- **Appending an item**:
  ```python
  fruits.append("orange")
  ```
- **Inserting an item**:
  ```python
  fruits.insert(1, "grape")
  ```
- **Removing an item**:
  ```python
  fruits.remove("apple")
  ```
- **Slicing a list**:
  ```python
  print(fruits[1:3])  # Output: ['blueberry', 'cherry']
  ```

---

### **Advanced List Operations**

#### **List Comprehension**
A concise way to create lists.
```python
squares = [x**2 for x in range(5)]
print(squares)  # Output: [0, 1, 4, 9, 16]
```

#### **Sorting and Reversing**
```python
numbers = [5, 2, 9, 1]
numbers.sort()  # Ascending order
numbers.reverse()  # Reverse the list
```

#### **Nested Lists**
Lists inside lists.
```python
matrix = [[1, 2], [3, 4], [5, 6]]
print(matrix[1][0])  # Output: 3
```

---

## **3. Tuples**
A tuple is an immutable sequence of elements.

### **Basic Concepts**

#### **Creating a Tuple**
```python
numbers = (1, 2, 3)
mixed = (1, "hello", 3.14)
```

#### **Accessing Elements**
```python
print(numbers[1])  # Output: 2
print(numbers[-1])  # Output: 3
```

---

### **Advanced Tuple Operations**

#### **Unpacking Tuples**
```python
coordinates = (10, 20)
x, y = coordinates
print(x)  # Output: 10
```

#### **Using Tuples as Dictionary Keys**
Tuples can be used as keys because they are immutable.
```python
locations = {(10, 20): "Park", (30, 40): "Mall"}
print(locations[(10, 20)])  # Output: Park
```

---

## **4. Dictionaries**
A dictionary stores key-value pairs, where keys must be unique.

### **Basic Concepts**

#### **Creating a Dictionary**
```python
student = {"name": "Alice", "age": 20, "grade": "A"}
```

#### **Accessing Values**
```python
print(student["name"])  # Output: Alice
```

#### **Adding and Modifying Key-Value Pairs**
```python
student["age"] = 21  # Modify
student["city"] = "New York"  # Add
```

#### **Removing Key-Value Pairs**
```python
del student["grade"]
```

---

### **Advanced Dictionary Operations**

#### **Iterating Over Dictionaries**
```python
for key, value in student.items():
    print(f"{key}: {value}")
```

#### **Dictionary Comprehension**
```python
squares = {x: x**2 for x in range(5)}
print(squares)  # Output: {0: 0, 1: 1, 2: 4, 3: 9, 4: 16}
```

#### **Merging Dictionaries**
```python
dict1 = {"a": 1, "b": 2}
dict2 = {"b": 3, "c": 4}
merged = {**dict1, **dict2}
print(merged)  # Output: {'a': 1, 'b': 3, 'c': 4}
```

---

## **5. Comparison Between Lists, Tuples, and Dictionaries**

| Feature             | List           | Tuple         | Dictionary       |
|---------------------|----------------|---------------|------------------|
| Mutable             | Yes            | No            | Yes              |
| Ordered             | Yes            | Yes           | No
| Allows Duplicates   | Yes            | Yes           | No               |
| Indexed Access      | Yes            | Yes           | No               |

---

## **6. Exercises**

### **Basic**:
1. Create a list of 5 fruits and print each fruit.
2. Create a tuple of 3 numbers and print their sum.
3. Create a dictionary of a student’s details (name, age, and grade) and print the values.

### **Intermediate**:
4. Write a program to find the largest number in a list.
5. Write a program to convert a list of tuples into a dictionary.
   ```python
   # Example input
   data = [("name", "Alice"), ("age", 25)]
   # Expected output: {"name": "Alice", "age": 25"}
   ```

6. Write a program to remove duplicates from a list.

### **Advanced**:
7. Write a program to create a dictionary where keys are numbers from 1 to 5, and values are their squares.
8. Write a program to count the frequency of each character in a string using a dictionary.
9. Given a list of dictionaries representing employees, filter out employees earning more than $50,000.

---

## **7. Real-World Applications**
1. **Lists**: Storing ordered collections like items in a cart.
2. **Tuples**: Representing fixed data like coordinates or configurations.
3. **Dictionaries**: Mapping data like user profiles or JSON-like structures.

---

