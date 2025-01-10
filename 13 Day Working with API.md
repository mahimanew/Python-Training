### **1. Introduction to APIs and Data**

An **API** allows different software applications to communicate with each other. **REST (Representational State Transfer)** is one of the most common architectural styles used for building web services. APIs that follow REST principles are referred to as **REST APIs**.

- **JSON (JavaScript Object Notation)** is the most commonly used data format for communication between clients and servers in REST APIs.
- **REST APIs** are stateless, meaning each request from a client contains all the information necessary to understand and process the request.

#### **1.1. Making HTTP Requests**

To work with APIs in Python, we use the `requests` library, which allows you to send HTTP requests to a server and handle the response.

---

### **2. Basic HTTP Requests**

#### **2.1. Sending a GET Request**

The **GET** method is used to retrieve data from a server. It is the most common type of HTTP request.

```python
import requests

response = requests.get("https://jsonplaceholder.typicode.com/posts")
print(response.status_code)  # Status code (200 indicates success)
print(response.json())  # Output the response in JSON format
```

Here, we are sending a GET request to the JSONPlaceholder API, which provides fake data for testing purposes. The `response.json()` method converts the returned JSON data into a Python dictionary.

#### **2.2. Sending a POST Request**

The **POST** method is used to send data to the server to create a new resource. We send data in the body of the request, usually in JSON format.

```python
import requests
import json

data = {
    "title": "New Post",
    "body": "This is a new post created via the POST request.",
    "userId": 1
}

response = requests.post("https://jsonplaceholder.typicode.com/posts", json=data)
print(response.status_code)  # Status code
print(response.json())  # The newly created post's details
```

In this example, we send JSON data using the `json` argument, which ensures the data is correctly formatted.

---

### **3. Working with JSON Data**

Most modern APIs use **JSON** as the format for sending and receiving data. You can parse JSON data easily in Python using the `json` module.

#### **3.1. Parsing JSON**

You can parse JSON data into Python dictionaries with the `json` module. JSON data typically consists of key-value pairs.

```python
import json

# Sample JSON string
json_data = '{"name": "John", "age": 30, "city": "New York"}'

# Convert JSON string to Python dictionary
python_dict = json.loads(json_data)
print(python_dict)  # Output: {'name': 'John', 'age': 30, 'city': 'New York'}
```

#### **3.2. Converting Python Objects to JSON**

You can convert Python objects (like dictionaries) to JSON format using the `json.dumps()` method.

```python
import json

python_dict = {"name": "John", "age": 30, "city": "New York"}

# Convert Python dictionary to JSON string
json_data = json.dumps(python_dict)
print(json_data)  # Output: {"name": "John", "age": 30, "city": "New York"}
```

---

### **4. Authentication and Authorization**

Many APIs require authentication to ensure that only authorized users can access the resources. There are multiple ways to authenticate with APIs, including **API keys**, **OAuth**, and **Basic Authentication**.

#### **4.1. Using API Keys**

Some APIs use an API key for authentication. You can pass this key in the request header or URL parameters.

```python
import requests

url = "https://api.example.com/data"
headers = {"Authorization": "Bearer YOUR_API_KEY"}
response = requests.get(url, headers=headers)

print(response.status_code)
print(response.json())
```

#### **4.2. Using Basic Authentication**

Some APIs require Basic Authentication, where you pass your username and password as part of the HTTP request headers.

```python
from requests.auth import HTTPBasicAuth
import requests

url = "https://api.example.com/data"
response = requests.get(url, auth=HTTPBasicAuth('username', 'password'))

print(response.status_code)
print(response.json())
```

---

### **5. Advanced HTTP Requests**

#### **5.1. Handling Timeouts and Errors**

When making HTTP requests, it's important to handle timeouts and errors gracefully.

```python
import requests

try:
    response = requests.get("https://jsonplaceholder.typicode.com/posts", timeout=5)
    response.raise_for_status()  # Raise an exception for 4xx/5xx status codes
    print(response.json())
except requests.exceptions.Timeout:
    print("Request timed out!")
except requests.exceptions.RequestException as e:
    print(f"An error occurred: {e}")
```

#### **5.2. Sending Data with PUT and DELETE Requests**

- **PUT**: Used to update an existing resource.
- **DELETE**: Used to delete a resource.

```python
# PUT Request
data = {
    "id": 1,
    "title": "Updated Title",
    "body": "Updated content",
    "userId": 1
}
response = requests.put("https://jsonplaceholder.typicode.com/posts/1", json=data)
print(response.status_code)
print(response.json())

# DELETE Request
response = requests.delete("https://jsonplaceholder.typicode.com/posts/1")
print(response.status_code)
```

---

### **6. Using REST APIs with Query Parameters**

REST APIs often accept query parameters to filter and modify the data returned. Query parameters are added to the URL after a `?` symbol, with each parameter separated by `&`.

#### **6.1. Example of Query Parameters**

```python
params = {"userId": 1}
response = requests.get("https://jsonplaceholder.typicode.com/posts", params=params)
print(response.json())  # Posts related to userId 1
```

---

### **7. Advanced Techniques in API Interaction**

#### **7.1. Pagination in APIs**

Some APIs return large datasets and may paginate the results. You can use query parameters like `page` and `limit` to get data in smaller chunks.

```python
params = {"_page": 1, "_limit": 5}
response = requests.get("https://jsonplaceholder.typicode.com/posts", params=params)
print(response.json())
```

#### **7.2. Handling Rate Limits**

Many APIs limit the number of requests that can be made in a certain period to prevent abuse. You can check the rate limit in the response headers and implement delays if necessary.

```python
import time
import requests

response = requests.get("https://api.example.com/data")
rate_limit = response.headers.get("X-RateLimit-Remaining")

if int(rate_limit) == 0:
    reset_time = int(response.headers.get("X-RateLimit-Reset"))
    wait_time = reset_time - int(time.time())
    print(f"Rate limit exceeded, retrying in {wait_time} seconds...")
    time.sleep(wait_time)
```

#### **7.3. Handling Webhooks**

Webhooks allow your server to receive real-time data from an API when specific events occur. This is commonly used in payment systems, social media, and e-commerce platforms.

```python
from flask import Flask, request

app = Flask(__name__)

@app.route('/webhook', methods=['POST'])
def webhook():
    data = request.json  # Incoming JSON data from the API
    print(data)  # Handle the data
    return "Webhook received!"

if __name__ == '__main__':
    app.run(debug=True)
```

---

### **8. Best Practices for Working with APIs**

- **Use environment variables**: Avoid hardcoding sensitive information like API keys in your code. Use environment variables to keep them secure.
- **Handle errors properly**: Always check for errors (e.g., invalid status codes, timeouts) and handle them gracefully.
- **Optimize requests**: Use pagination for large datasets, and limit the number of requests to prevent hitting rate limits.
- **Document API usage**: When using APIs in a team environment, document how to authenticate, send requests, and handle responses.

---

### **9. Exercises for Day 14:**

1. **Basic:**
   - Write a Python script that fetches data from a public REST API (e.g., JSONPlaceholder) and displays the data.
   - Create a Python script that sends a POST request with JSON data to a mock API.

2. **Intermediate:**
   - Fetch posts by a specific user from the JSONPlaceholder API using query parameters.
   - Handle timeouts and errors in an API request.

3. **Advanced:**
   - Write a Python script that interacts with an API that requires authentication (e.g., Twitter API, GitHub API) and fetches user data.
   - Implement pagination to fetch a large dataset from an API, processing the results in chunks.

