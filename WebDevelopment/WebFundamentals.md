
---

### **HTTP/HTTPS**

#### **1. Explain the HTTP Request-Response Model.**
**Answer**:  
- The **request-response model** is the communication pattern where a client sends a request to a server, and the server processes the request and sends back a response.
- **Request**: Contains a method (e.g., GET, POST), headers, an optional body, and a URL specifying the resource.
- **Response**: Contains status codes (e.g., 200, 404), headers, and an optional body containing data or an error message.

---

#### **2. What are the differences between HTTP and HTTPS?**
**Answer**:
| Aspect        | HTTP                                | HTTPS                                |
|---------------|-------------------------------------|--------------------------------------|
| **Security**  | Unsecured                          | Encrypted with SSL/TLS              |
| **Port**      | Uses port 80                       | Uses port 443                       |
| **Data**      | Sent in plain text                 | Encrypted data prevents interception |
| **Usage**     | Suitable for non-sensitive data    | Used for sensitive data like login or payment |

---

#### **3. What is a status code? Can you give examples?**
**Answer**:
Status codes indicate the result of an HTTP request. Examples include:
- **200 OK**: Request succeeded.
- **404 Not Found**: The requested resource doesn’t exist.
- **500 Internal Server Error**: A server-side issue occurred.

---

#### **4. What is CORS, and why is it important?**
**Answer**:
- **CORS (Cross-Origin Resource Sharing)** is a security feature that restricts how resources on a server can be requested by a different origin.
- It is important to prevent unauthorized access and ensure that only trusted domains can access sensitive data.
- CORS headers (e.g., `Access-Control-Allow-Origin`) specify which domains and methods are allowed.

---

#### **5. What are some common HTTP methods?**
**Answer**:
- **GET**: Retrieve data from a server.
- **POST**: Send data to the server, typically to create a new resource.
- **PUT**: Update an existing resource or create it if it doesn’t exist.
- **DELETE**: Remove a resource from the server.
- **OPTIONS**: Preflight request to check server permissions for CORS.

---

### **APIs**

#### **6. What is an API, and how is it used?**
**Answer**:
- **API (Application Programming Interface)**: A set of protocols and tools for building software applications.
- It allows communication between different systems, e.g., a frontend app making a request to a backend server.

---

#### **7. What are the core principles of RESTful APIs?**
**Answer**:
1. **Statelessness**: Each request contains all the information needed for processing.
2. **Client-Server Architecture**: Clear separation of frontend and backend concerns.
3. **Uniform Interface**: Consistent endpoints and methods.
4. **Cacheability**: Responses indicate if caching is allowed.
5. **Resource Identification**: Resources identified by URIs (e.g., `/users/123`).

---

#### **8. What is the difference between REST and SOAP?**
**Answer**:
| Aspect        | REST                                  | SOAP                                  |
|---------------|---------------------------------------|---------------------------------------|
| **Protocol**  | Uses HTTP                            | Uses XML-based messaging protocol     |
| **Flexibility** | Supports multiple formats (JSON, XML)| Strictly uses XML                    |
| **State**     | Stateless                            | Can be stateful                      |
| **Performance** | Faster due to JSON and less overhead | Slower due to XML parsing            |

---

#### **9. How do you secure an API?**
**Answer**:
1. **Authentication**: Use methods like API keys, OAuth, or JWT.
2. **Encryption**: Use HTTPS to encrypt data in transit.
3. **Rate Limiting**: Limit the number of requests from a single client.
4. **Input Validation**: Prevent injection attacks by sanitizing input.
5. **CORS**: Restrict access to trusted origins.

---

#### **10. How do you handle errors in a REST API?**
**Answer**:
1. Use proper **HTTP status codes** (e.g., `400 Bad Request`, `500 Internal Server Error`).
2. Provide **error messages** with details in the response body.
   Example response:
   ```json
   {
     "error": "Invalid data",
     "details": "The email field is required."
   }
   ```

---

#### **11. How would you create an API endpoint?**
**Answer**:
1. **Define the resource**: Decide what resource (e.g., `/products`) the API should expose.
2. **Use appropriate methods**:
   - `GET /products`: Get all products.
   - `POST /products`: Add a new product.
   - `PUT /products/{id}`: Update a product.
   - `DELETE /products/{id}`: Delete a product.
3. **Handle errors**: Return proper status codes for invalid inputs or server issues.
4. **Document**: Use tools like Swagger for clear documentation.

---

#### **12. How do you consume an API?**
**Answer**:
- Use HTTP clients like `fetch` (JavaScript) or libraries like `axios`.
- Example with `fetch`:
   ```javascript
   fetch('https://api.example.com/data', {
     method: 'GET',
     headers: {
       'Authorization': 'Bearer token'
     }
   })
   .then(response => response.json())
   .then(data => console.log(data))
   .catch(error => console.error('Error:', error));
   ```

---

#### **13. What is a preflight request in CORS?**
**Answer**:
A **preflight request** is a preliminary request made using the `OPTIONS` method to check whether the server allows the actual request (e.g., with custom headers or methods). The server responds with headers like `Access-Control-Allow-Methods` to indicate permissions.

---

#### **14. Can you explain the difference between PUT and POST?**
**Answer**:
| Aspect            | PUT                                  | POST                                  |
|--------------------|--------------------------------------|---------------------------------------|
| **Purpose**        | Update or create a resource         | Create a new resource                |
| **Idempotence**    | Idempotent (repeated calls have the same effect) | Not idempotent                      |
| **Example**        | `PUT /users/123` updates user 123   | `POST /users` creates a new user     |

---
