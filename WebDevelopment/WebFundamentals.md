### **Web Fundamentals**

---

### **1. HTTP/HTTPS**
HTTP (HyperText Transfer Protocol) and HTTPS (HTTP Secure) are foundational protocols for web communication. Here are the details:

#### **Request-Response Model**
- **Overview**: The client (browser or application) sends an HTTP request to a server, which processes the request and sends back an HTTP response.
- **Structure of an HTTP Request**:
  1. **Request Line**: Contains the method (GET, POST, PUT, etc.), URL, and HTTP version.
  2. **Headers**: Provide metadata like content type, user-agent, and authentication details.
  3. **Body** (Optional): Contains data, usually for POST/PUT requests.
- **Structure of an HTTP Response**:
  1. **Status Line**: Contains the HTTP version, status code, and reason phrase.
  2. **Headers**: Similar to request headers, providing metadata for the response.
  3. **Body**: Contains the requested resource (e.g., HTML, JSON) or error details.

#### **Status Codes**
- **1xx Informational**: Request received, continuing process.
  - **100 Continue**: Initial part of the request has been received.
- **2xx Success**: Request successfully processed.
  - **200 OK**: Standard success response.
  - **201 Created**: Resource successfully created.
- **3xx Redirection**: Further action needed to complete the request.
  - **301 Moved Permanently**: Resource permanently moved to a new URL.
  - **302 Found**: Temporary redirection.
- **4xx Client Errors**: Issues with the request.
  - **400 Bad Request**: Invalid request syntax or parameters.
  - **401 Unauthorized**: Authentication required.
  - **403 Forbidden**: Server refuses to authorize.
  - **404 Not Found**: Resource not found.
- **5xx Server Errors**: Issues on the server side.
  - **500 Internal Server Error**: Generic server error.
  - **503 Service Unavailable**: Server temporarily unable to handle the request.

#### **CORS (Cross-Origin Resource Sharing)**
- **Purpose**: Allows a server to specify who can access its resources from another origin.
- **Same-Origin Policy**: Browsers restrict requests to the same origin unless explicitly allowed.
- **Key Headers**:
  - `Access-Control-Allow-Origin`: Specifies allowed origins.
  - `Access-Control-Allow-Methods`: Lists HTTP methods allowed (e.g., GET, POST).
  - `Access-Control-Allow-Headers`: Lists custom headers allowed in requests.
- **Preflight Requests**: Automatically sent by browsers using the OPTIONS method to check permissions.

---

### **2. APIs**
APIs (Application Programming Interfaces) allow communication between software applications.

#### **RESTful Principles**
REST (Representational State Transfer) is an architectural style for building APIs, emphasizing stateless communication and resource management.

1. **Statelessness**:
   - Each request from a client contains all information needed to process it.
   - The server does not store client state between requests.
2. **Client-Server Architecture**:
   - The client handles user interface and user experience.
   - The server manages data and logic.
3. **Uniform Interface**:
   - Use consistent endpoints and methods (e.g., `/users` for user data).
   - Follow standard conventions for HTTP methods:
     - **GET**: Retrieve resources.
     - **POST**: Create new resources.
     - **PUT/PATCH**: Update existing resources.
     - **DELETE**: Remove resources.
4. **Resource Identification**:
   - Resources are identified by URIs (e.g., `/api/v1/products/123`).
5. **Representation**:
   - Resources can be represented in formats like JSON or XML.
6. **Stateless Cacheability**:
   - Responses indicate whether they can be cached.

#### **Creating APIs**
1. **Define Endpoints**:
   - List all resources and their CRUD operations.
   - Example:
     - GET `/users`: Get a list of users.
     - POST `/users`: Create a new user.
2. **Use Proper HTTP Methods**:
   - Follow REST conventions for operations.
3. **Handle Errors Gracefully**:
   - Use appropriate status codes and descriptive error messages.
4. **Secure the API**:
   - Use HTTPS to encrypt data in transit.
   - Implement authentication (e.g., JWT, OAuth).
5. **Documentation**:
   - Provide clear API documentation (e.g., Swagger, Postman).

#### **Consuming APIs**
1. **HTTP Clients**:
   - Use libraries like `fetch` (JavaScript), `axios`, or tools like Postman.
2. **Steps to Consume**:
   - **Send Request**: Use the correct method, URL, headers, and body.
   - **Parse Response**: Handle the response format (JSON, XML).
   - **Handle Errors**: Manage client-side and server-side errors.
3. **Authentication**:
   - Include tokens or API keys in headers.
   - Example:
     ```javascript
     fetch('https://api.example.com/data', {
       method: 'GET',
       headers: {
         'Authorization': 'Bearer your-token-here'
       }
     });
     ```

---

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
