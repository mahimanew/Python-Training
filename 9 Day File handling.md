

### **1. Introduction to File Handling in Python**
File handling in Python is done using built-in functions in the `open()` function, which opens a file and returns a file object. Once the file is open, you can perform various operations like reading, writing, or appending data.

---

### **2. Opening Files**
To open a file, use the `open()` function. The function takes at least one argument: the file path, and optionally, a mode.

#### **Syntax:**
```python
file = open("filename", "mode")
```

**Modes for opening files:**
- `"r"`: Read (default mode). Opens the file for reading.
- `"w"`: Write. Opens the file for writing (creates the file if it doesn't exist, or truncates the file if it exists).
- `"a"`: Append. Opens the file for appending (creates the file if it doesn't exist).
- `"b"`: Binary mode. Used for reading or writing binary files (e.g., images).
- `"x"`: Exclusive creation. Opens the file for exclusive creation, fails if the file already exists.

#### **Example:**
```python
file = open("example.txt", "r")
```

---

### **3. Reading Files**
Once the file is opened, you can read its contents using the following methods:

#### **`read()` Method:**
Reads the entire content of the file.
```python
file = open("example.txt", "r")
content = file.read()
print(content)
file.close()
```

#### **`readline()` Method:**
Reads one line at a time.
```python
file = open("example.txt", "r")
line = file.readline()
print(line)
file.close()
```

#### **`readlines()` Method:**
Reads all lines of the file and returns them as a list.
```python
file = open("example.txt", "r")
lines = file.readlines()
print(lines)
file.close()
```

---

### **4. Writing to Files**
Writing to files allows you to store information. There are different modes for writing:

#### **`write()` Method:**
Writes a string to the file.
```python
file = open("example.txt", "w")
file.write("Hello, Python!")
file.close()
```

#### **`writelines()` Method:**
Writes a list of strings to the file.
```python
file = open("example.txt", "w")
lines = ["Hello, Python!", "Welcome to file handling."]
file.writelines(lines)
file.close()
```

---

### **5. Closing Files**
It is important to close files after performing operations to free up system resources. You can use the `close()` method:

```python
file = open("example.txt", "r")
# Perform operations
file.close()
```

---

### **6. Using `with` Statement for File Handling**
Instead of manually opening and closing files, you can use the `with` statement. This ensures that the file is properly closed after the block of code is executed, even if an error occurs.

#### **Syntax:**
```python
with open("example.txt", "r") as file:
    # Perform operations
    content = file.read()
    print(content)
```

---

### **7. File Operations:**
You can perform various operations on files, such as checking if a file exists, renaming files, or deleting files.

#### **`os` Module for File Operations:**
```python
import os

# Check if file exists
if os.path.exists("example.txt"):
    print("File exists.")

# Renaming the file
os.rename("old_name.txt", "new_name.txt")

# Removing a file
os.remove("example.txt")
```

---

### **8. Working with Binary Files**
Sometimes you need to read or write binary files, such as images or videos. This is done using the binary mode (`"rb"`, `"wb"`, etc.).

#### **Reading Binary File:**
```python
with open("image.jpg", "rb") as file:
    content = file.read()
    print(content)
```

#### **Writing Binary File:**
```python
with open("new_image.jpg", "wb") as file:
    content = b"Some binary data"
    file.write(content)
```

---

### **9. Advanced File Handling Concepts**
---

#### **9.1. File Pointer**
The file pointer keeps track of the current position when reading or writing. You can move the pointer using methods like `seek()` and `tell()`.

- **`seek()`**: Moves the pointer to a specific position in the file.
- **`tell()`**: Returns the current position of the file pointer.

#### **Example:**
```python
with open("example.txt", "r") as file:
    file.seek(10)  # Move the pointer to the 10th byte
    print(file.read())  # Read from the 10th byte onward
    print(file.tell())  # Get the current file pointer position
```

---

#### **9.2. File Handling with CSV Files**
CSV (Comma Separated Values) files are commonly used for data storage. Python provides a `csv` module for reading and writing CSV files.

##### **Reading CSV Files:**
```python
import csv

with open("data.csv", mode="r") as file:
    csv_reader = csv.reader(file)
    for row in csv_reader:
        print(row)
```

##### **Writing to CSV Files:**
```python
import csv

data = [["Name", "Age"], ["Alice", 25], ["Bob", 30]]
with open("data.csv", mode="w", newline="") as file:
    csv_writer = csv.writer(file)
    csv_writer.writerows(data)
```

---

#### **9.3. File Handling with JSON**
JSON (JavaScript Object Notation) files are widely used for data exchange. Python provides a `json` module for handling JSON files.

##### **Reading JSON Files:**
```python
import json

with open("data.json", "r") as file:
    data = json.load(file)
    print(data)
```

##### **Writing JSON Files:**
```python
import json

data = {"name": "Alice", "age": 25}
with open("data.json", "w") as file:
    json.dump(data, file)
```

---

### **10. Exercises for Day 9:**

1. **Basic:**
   - Write a program to read a text file and print its content line by line.
   - Write a program to create a file and write some content into it.

2. **Intermediate:**
   - Write a program that takes input from the user and appends it to an existing file.
   - Write a program that counts the number of lines, words, and characters in a text file.

3. **Advanced:**
   - Write a program that reads a binary file (e.g., an image), modifies it, and writes the modified data to another file.
   - Create a program to read and write to a CSV file (create a contact list with fields like name, email, and phone number).
   - Write a program that converts a dictionary to a JSON file and reads it back.

---
