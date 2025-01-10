
### **1. Introduction to Databases**
A **database** is a structured collection of data that can be easily accessed, managed, and updated. In relational databases, data is stored in tables with rows and columns, and SQL (Structured Query Language) is used to interact with these databases.

- **SQLite** is a self-contained, serverless, and zero-configuration database engine that is widely used in applications for local storage.
- Other databases include MySQL, PostgreSQL, and Oracle, but SQLite is perfect for learning SQL and Python integration.

#### **Basic Concepts of Databases**
- **Tables**: Collection of rows and columns where data is stored.
- **Rows (Records)**: Each entry in the table.
- **Columns (Fields)**: Different attributes or categories of data in the table.

---

### **2. SQLite Basics in Python**

#### **2.1. Setting up SQLite Database**
Python has a built-in library, `sqlite3`, which allows you to work with SQLite databases. You do not need to install anything extra as it's included by default in Python.

```python
import sqlite3

# Connect to a database (it will create the database file if it doesn't exist)
conn = sqlite3.connect('mydatabase.db')

# Create a cursor object to execute SQL commands
cursor = conn.cursor()

# Create a table
cursor.execute('''
CREATE TABLE IF NOT EXISTS users (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    name TEXT,
    age INTEGER,
    email TEXT
)
''')

# Commit changes and close the connection
conn.commit()
conn.close()
```

In this example:
- `sqlite3.connect()` connects to an SQLite database. If the database file does not exist, it is created.
- `cursor.execute()` executes an SQL command.
- `conn.commit()` commits the changes (i.e., saves them to the database).
- `conn.close()` closes the connection to the database.

---

### **3. Basic SQL Commands**
- **SELECT**: Retrieves data from one or more tables.
- **INSERT**: Adds new rows to a table.
- **UPDATE**: Modifies existing rows in a table.
- **DELETE**: Removes rows from a table.

#### **3.1. Inserting Data into a Table**
You can insert data into a table using the `INSERT INTO` command.

```python
# Insert a record into the 'users' table
conn = sqlite3.connect('mydatabase.db')
cursor = conn.cursor()

cursor.execute("INSERT INTO users (name, age, email) VALUES (?, ?, ?)", ("John Doe", 28, "john@example.com"))

# Commit changes
conn.commit()
conn.close()
```

In the `INSERT INTO` statement:
- `?` is a placeholder for parameters, which helps prevent **SQL injection** attacks by ensuring values are properly escaped.

#### **3.2. Querying Data with SELECT**
To fetch data from the database, use the `SELECT` command.

```python
# Retrieve all records from the 'users' table
conn = sqlite3.connect('mydatabase.db')
cursor = conn.cursor()

cursor.execute("SELECT * FROM users")
rows = cursor.fetchall()  # Fetch all rows

for row in rows:
    print(row)

conn.close()
```

This fetches all rows from the `users` table. You can use `SELECT` with filtering and sorting options.

#### **3.3. Filtering Data with WHERE**
To filter data, use the `WHERE` clause in your query.

```python
# Retrieve users who are over 25 years old
conn = sqlite3.connect('mydatabase.db')
cursor = conn.cursor()

cursor.execute("SELECT * FROM users WHERE age > 25")
rows = cursor.fetchall()

for row in rows:
    print(row)

conn.close()
```

You can also use comparison operators (`=`, `>`, `<`, `>=`, `<=`, `!=`) and logical operators (`AND`, `OR`).

#### **3.4. Updating Data with UPDATE**
Use the `UPDATE` statement to modify existing data.

```python
# Update the email address of a user with id 1
conn = sqlite3.connect('mydatabase.db')
cursor = conn.cursor()

cursor.execute("UPDATE users SET email = ? WHERE id = ?", ("newemail@example.com", 1))

conn.commit()
conn.close()
```

#### **3.5. Deleting Data with DELETE**
Use the `DELETE` statement to remove data.

```python
# Delete a user with id 1
conn = sqlite3.connect('mydatabase.db')
cursor = conn.cursor()

cursor.execute("DELETE FROM users WHERE id = ?", (1,))

conn.commit()
conn.close()
```

---

### **4. Intermediate SQL Concepts**
- **Sorting**: Use the `ORDER BY` clause to sort results.
- **Joins**: Combine data from multiple tables using `JOIN`.
- **Aggregation**: Use functions like `COUNT()`, `SUM()`, `AVG()` to perform calculations on data.

#### **4.1. Sorting Data**
You can sort data using the `ORDER BY` clause.

```python
# Retrieve users sorted by age in descending order
conn = sqlite3.connect('mydatabase.db')
cursor = conn.cursor()

cursor.execute("SELECT * FROM users ORDER BY age DESC")
rows = cursor.fetchall()

for row in rows:
    print(row)

conn.close()
```

#### **4.2. Using Joins**
A **JOIN** combines data from two or more tables based on a related column.

```python
# Example: Joining two tables (assuming a 'posts' table exists)
cursor.execute('''
CREATE TABLE IF NOT EXISTS posts (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    user_id INTEGER,
    title TEXT,
    body TEXT,
    FOREIGN KEY (user_id) REFERENCES users(id)
)
''')

# Insert sample data
cursor.execute("INSERT INTO posts (user_id, title, body) VALUES (?, ?, ?)", (1, "My First Post", "This is the body of the post"))

# Join users and posts
cursor.execute('''
SELECT users.name, posts.title
FROM users
JOIN posts ON users.id = posts.user_id
''')

rows = cursor.fetchall()
for row in rows:
    print(row)

conn.close()
```

In this example, we join the `users` table with the `posts` table to get the user's name and their post title.

#### **4.3. Aggregation Functions**
SQL provides aggregate functions such as `COUNT()`, `SUM()`, `AVG()`, `MIN()`, and `MAX()` for performing calculations on data.

```python
# Get the total number of users
cursor.execute("SELECT COUNT(*) FROM users")
count = cursor.fetchone()[0]
print("Total users:", count)
```

---

### **5. Advanced SQLite Concepts**

#### **5.1. Transactions**
A **transaction** allows you to execute multiple SQL commands as a single unit, ensuring atomicity (either all operations succeed, or none do).

```python
conn = sqlite3.connect('mydatabase.db')
cursor = conn.cursor()

# Start a transaction
try:
    cursor.execute("INSERT INTO users (name, age, email) VALUES (?, ?, ?)", ("Alice", 30, "alice@example.com"))
    cursor.execute("INSERT INTO users (name, age, email) VALUES (?, ?, ?)", ("Bob", 25, "bob@example.com"))
    conn.commit()  # Commit the transaction
except sqlite3.Error:
    conn.rollback()  # Rollback in case of an error
    print("Transaction failed")

conn.close()
```

#### **5.2. Indexing**
An **index** improves the performance of queries by allowing faster retrieval of data. It’s especially useful for large databases.

```python
# Create an index on the 'email' column
cursor.execute("CREATE INDEX IF NOT EXISTS idx_email ON users (email)")
conn.commit()
```

#### **5.3. Foreign Keys**
A **foreign key** is a column that creates a relationship between two tables. It references the primary key of another table.

```python
# Creating a foreign key constraint
cursor.execute('''
CREATE TABLE IF NOT EXISTS orders (
    id INTEGER PRIMARY KEY,
    user_id INTEGER,
    amount REAL,
    FOREIGN KEY(user_id) REFERENCES users(id)
)
''')
```

---

### **6. Best Practices for Working with Databases**
- Always use parameterized queries (with placeholders) to avoid SQL injection.
- Ensure proper error handling in database operations.
- Use **transactions** to group multiple operations and ensure atomicity.
- Optimize queries using **indexes** on frequently queried columns.
- Regularly back up the database to avoid data loss.

---

