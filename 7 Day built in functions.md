## **1. Introduction to Built-in Functions**
Python comes with many built-in functions that allow you to perform common tasks without needing to write custom code. These functions are readily available and help speed up development.

---

## **2. Basic Built-in Functions**

### **a. Input/Output Functions**
1. **`print()`**: Prints output to the console.
   ```python
   print("Hello, World!")
   ```

2. **`input()`**: Takes user input.
   ```python
   name = input("Enter your name: ")
   print(f"Hello, {name}!")
   ```

---

### **b. Type Conversion Functions**
1. **`int()`**: Converts a value to an integer.
   ```python
   num = int("10")
   print(num + 5)  # Output: 15
   ```

2. **`float()`**: Converts a value to a floating-point number.
   ```python
   num = float("3.14")
   ```

3. **`str()`**: Converts a value to a string.
   ```python
   num = 42
   print("The number is " + str(num))
   ```

4. **`bool()`**: Converts a value to a boolean.
   ```python
   print(bool(0))  # Output: False
   print(bool(1))  # Output: True
   ```

---

### **c. Mathematical Functions**
1. **`abs()`**: Returns the absolute value of a number.
   ```python
   print(abs(-5))  # Output: 5
   ```

2. **`pow()`**: Returns the result of a number raised to a power.
   ```python
   print(pow(2, 3))  # Output: 8
   ```

3. **`round()`**: Rounds a number to the nearest integer or specified decimal places.
   ```python
   print(round(3.14159, 2))  # Output: 3.14
   ```

---

## **3. Intermediate Built-in Functions**

### **a. Collection Functions**
1. **`len()`**: Returns the length of a sequence.
   ```python
   print(len([1, 2, 3]))  # Output: 3
   ```

2. **`max()` and `min()`**: Return the maximum and minimum values of a sequence.
   ```python
   print(max([10, 20, 30]))  # Output: 30
   print(min([10, 20, 30]))  # Output: 10
   ```

3. **`sum()`**: Returns the sum of elements in a sequence.
   ```python
   print(sum([1, 2, 3]))  # Output: 6
   ```

4. **`sorted()`**: Returns a sorted version of a sequence.
   ```python
   print(sorted([3, 1, 2]))  # Output: [1, 2, 3]
   ```

---

### **b. String Functions**
1. **`ord()`**: Returns the Unicode code point of a character.
   ```python
   print(ord('A'))  # Output: 65
   ```

2. **`chr()`**: Returns the character for a Unicode code point.
   ```python
   print(chr(65))  # Output: 'A'
   ```

---

### **c. Functional Programming Functions**
1. **`map()`**: Applies a function to each item in an iterable.
   ```python
   nums = [1, 2, 3]
   squared = list(map(lambda x: x**2, nums))
   print(squared)  # Output: [1, 4, 9]
   ```

2. **`filter()`**: Filters elements based on a condition.
   ```python
   nums = [1, 2, 3, 4]
   evens = list(filter(lambda x: x % 2 == 0, nums))
   print(evens)  # Output: [2, 4]
   ```

3. **`zip()`**: Combines multiple iterables into tuples.
   ```python
   names = ["Alice", "Bob"]
   ages = [25, 30]
   combined = list(zip(names, ages))
   print(combined)  # Output: [('Alice', 25), ('Bob', 30)]
   ```

---

## **4. Advanced Built-in Functions**

### **a. Object Introspection Functions**
1. **`type()`**: Returns the type of an object.
   ```python
   print(type(10))  # Output: <class 'int'>
   ```

2. **`id()`**: Returns the memory address of an object.
   ```python
   print(id(10))
   ```


---

### **b. Advanced Iteration Functions**
1. **`enumerate()`**: Returns an iterable with index and value pairs.
   ```python
   items = ["a", "b", "c"]
   for index, value in enumerate(items):
       print(index, value)
   ```

2. **`reversed()`**: Returns a reversed iterator.
   ```python
   print(list(reversed([1, 2, 3])))  # Output: [3, 2, 1]
   ```

---

### **c. Input and Output**
1. **`open()`**: Opens a file.
   ```python
   with open("example.txt", "r") as file:
       print(file.read())
   ```

2. **`help()`**: Displays the help documentation for an object.
   ```python
   help(print)
   ```

---

## **5. Exercises**

1. Write a program that takes two numbers as input, adds them, and prints the result using `input()` and `print()`.
2. Find the largest and smallest numbers in a list using `max()` and `min()`.
3. Use `zip()` to combine two lists into a dictionary.
4. Create a program to read a file and count the number of words in it using `open()` and `len()`.
---


## ** Bonus **

## **1. String Functions**

### **a. Case Conversion**
1. **`lower()`**: Converts all characters to lowercase.
   ```python
   text = "Hello World"
   print(text.lower())  # Output: hello world
   ```

2. **`upper()`**: Converts all characters to uppercase.
   ```python
   print(text.upper())  # Output: HELLO WORLD
   ```

3. **`capitalize()`**: Capitalizes the first character of the string.
   ```python
   print(text.capitalize())  # Output: Hello world
   ```

4. **`title()`**: Capitalizes the first letter of each word.
   ```python
   print(text.title())  # Output: Hello World
   ```

---

### **b. Searching and Checking**
1. **`find()`**: Returns the index of the first occurrence of a substring, or `-1` if not found.
   ```python
   print(text.find("World"))  # Output: 6
   ```

2. **`startswith()`**: Checks if the string starts with a specific prefix.
   ```python
   print(text.startswith("Hello"))  # Output: True
   ```

3. **`endswith()`**: Checks if the string ends with a specific suffix.
   ```python
   print(text.endswith("World"))  # Output: True
   ```

4. **`count()`**: Counts occurrences of a substring.
   ```python
   print(text.count("l"))  # Output: 3
   ```

---

### **c. Modification**
1. **`strip()`**: Removes whitespace (or specified characters) from the beginning and end of the string.
   ```python
   text = "  Hello  "
   print(text.strip())  # Output: Hello
   ```

2. **`replace()`**: Replaces occurrences of a substring with another string.
   ```python
   print(text.replace("World", "Python"))  # Output: Hello Python
   ```

3. **`split()`**: Splits a string into a list based on a delimiter.
   ```python
   words = "a,b,c".split(",")
   print(words)  # Output: ['a', 'b', 'c']
   ```

4. **`join()`**: Joins elements of a list into a string using a delimiter.
   ```python
   print(", ".join(["a", "b", "c"]))  # Output: a, b, c
   ```

---

### **d. Validation**
1. **`isalnum()`**: Returns `True` if all characters are alphanumeric.
   ```python
   print("abc123".isalnum())  # Output: True
   ```

2. **`isalpha()`**: Returns `True` if all characters are alphabetic.
   ```python
   print("abc".isalpha())  # Output: True
   ```

3. **`isdigit()`**: Returns `True` if all characters are digits.
   ```python
   print("123".isdigit())  # Output: True
   ```

4. **`isspace()`**: Returns `True` if all characters are whitespace.
   ```python
   print("   ".isspace())  # Output: True
   ```

---

## **2. List Functions**
1. **`append()`**: Adds an element to the end of the list.
   ```python
   numbers = [1, 2, 3]
   numbers.append(4)
   print(numbers)  # Output: [1, 2, 3, 4]
   ```

2. **`extend()`**: Adds elements from another list.
   ```python
   numbers.extend([5, 6])
   print(numbers)  # Output: [1, 2, 3, 4, 5, 6]
   ```

3. **`pop()`**: Removes and returns the last element (or the element at a specified index).
   ```python
   print(numbers.pop())  # Output: 6
   ```

4. **`index()`**: Returns the index of the first occurrence of an element.
   ```python
   print(numbers.index(3))  # Output: 2
   ```

5. **`count()`**: Counts the occurrences of a specific element.
   ```python
   print(numbers.count(2))  # Output: 1
   ```

---

## **3. Tuple Functions**
Tuples share many methods with lists (like `count()` and `index()`), but since they are immutable, modifying functions like `append()` and `pop()` are not available.

---

## **4. Dictionary Functions**
1. **`keys()`**: Returns all keys in the dictionary.
   ```python
   student = {"name": "Alice", "age": 20}
   print(student.keys())  # Output: dict_keys(['name', 'age'])
   ```

2. **`values()`**: Returns all values in the dictionary.
   ```python
   print(student.values())  # Output: dict_values(['Alice', 20])
   ```

3. **`items()`**: Returns all key-value pairs as tuples.
   ```python
   print(student.items())  # Output: dict_items([('name', 'Alice'), ('age', 20)])
   ```

4. **`get()`**: Returns the value for a key, or a default value if the key doesn’t exist.
   ```python
   print(student.get("name", "Unknown"))  # Output: Alice
   ```

5. **`update()`**: Updates the dictionary with new key-value pairs.
   ```python
   student.update({"grade": "A"})
   ```

---

## **5. Set Functions**
1. **`add()`**: Adds an element to the set.
   ```python
   my_set = {1, 2, 3}
   my_set.add(4)
   ```

2. **`remove()`**: Removes a specific element.
   ```python
   my_set.remove(2)
   ```

3. **`union()`**: Returns the union of two sets.
   ```python
   set1 = {1, 2, 3}
   set2 = {3, 4, 5}
   print(set1.union(set2))  # Output: {1, 2, 3, 4, 5}
   ```

4. **`intersection()`**: Returns the intersection of two sets.
   ```python
   print(set1.intersection(set2))  # Output: {3}
   ```

---

## **6. Miscellaneous Functions**
1. **`eval()`**: Evaluates a string as a Python expression.
   ```python
   print(eval("5 + 5"))  # Output: 10
   ```

2. **`any()`**: Returns `True` if at least one element in an iterable is `True`.
   ```python
   print(any([0, 1, 0]))  # Output: True
   ```

3. **`all()`**: Returns `True` if all elements in an iterable are `True`.
   ```python
   print(all([1, 1, 1]))  # Output: True
   ```

4. **`isinstance()`**: Checks if an object is an instance of a specific type.
   ```python
   print(isinstance(5, int))  # Output: True
   ```

---

