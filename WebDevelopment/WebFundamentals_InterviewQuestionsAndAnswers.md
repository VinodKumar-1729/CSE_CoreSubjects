
### **Basic Concepts**

1. **What is HTTP, and how does it work?**  
   HTTP (HyperText Transfer Protocol) is a stateless protocol used for communication between clients (like web browsers) and servers.  
   - **How it works:**  
     - A client sends an HTTP request to a server specifying a resource (e.g., a webpage).  
     - The server processes the request and sends back an HTTP response containing the requested resource or an error message.  

2. **Explain the difference between HTTP and HTTPS.**  
   - **HTTP:** Transfers data in plaintext, making it vulnerable to interception.  
   - **HTTPS:** Encrypts data using SSL/TLS, ensuring secure communication. HTTPS provides authentication, data integrity, and confidentiality.  

3. **What are the common HTTP methods? Provide examples.**  
   - **GET:** Retrieve data. Example: `GET /users/123` fetches user with ID 123.  
   - **POST:** Submit data. Example: `POST /users` adds a new user.  
   - **PUT:** Update existing data. Example: `PUT /users/123` updates user 123.  
   - **DELETE:** Remove data. Example: `DELETE /users/123` deletes user 123.  

4. **What is the purpose of the `Content-Type` header in HTTP?**  
   It specifies the media type of the request/response body (e.g., JSON, XML, HTML). This helps the recipient process the data appropriately.  
   Example: `Content-Type: application/json` indicates the body contains JSON data.

5. **How does an HTTP request and response cycle work?**  
   - **Request:** The client sends a request line (e.g., method and URL), headers, and an optional body.  
   - **Response:** The server sends a status line (e.g., HTTP version and status code), headers, and an optional body with the requested data.  

6. **Explain the term "stateless protocol" in the context of HTTP.**  
   HTTP does not retain information about previous interactions between the client and server. Each request is independent, requiring state management through cookies, sessions, or tokens if needed.

7. **What is the role of the `User-Agent` header in HTTP?**  
   The `User-Agent` header identifies the client making the request (e.g., browser or app). Servers can use this information to tailor responses.  
   Example: `User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64)`.

---

### **Advanced Topics**

1. **What is an HTTP status code? Explain the categories (1xx, 2xx, 3xx, 4xx, 5xx).**  
   Status codes indicate the result of an HTTP request:  
   - **1xx (Informational):** Request received, processing continues (e.g., 100 Continue).  
   - **2xx (Success):** Request was successful (e.g., 200 OK, 201 Created).  
   - **3xx (Redirection):** Client must take further action (e.g., 301 Moved Permanently, 304 Not Modified).  
   - **4xx (Client Errors):** Request error by the client (e.g., 400 Bad Request, 404 Not Found).  
   - **5xx (Server Errors):** Server failed to fulfill the request (e.g., 500 Internal Server Error, 503 Service Unavailable).

2. **What is CORS (Cross-Origin Resource Sharing), and how is it managed?**  
   - **CORS:** A mechanism that allows restricted resources on a web page to be accessed from a domain other than the one serving the page.  
   - **Managed through headers:**  
     - Server sends `Access-Control-Allow-Origin` in response to indicate which domains can access the resource.  
   Example: `Access-Control-Allow-Origin: https://example.com`.

3. **What is the role of SSL/TLS in HTTPS? Explain the handshake process.**  
   - **Role:** SSL/TLS encrypts data to ensure secure communication between client and server.  
   - **Handshake Process:**
     1. Client sends a "Hello" message with supported protocols and cipher suites.  
     2. Server responds with its "Hello" message, selecting the protocol and cipher suite.  
     3. Server sends its digital certificate.  
     4. Client verifies the certificate and generates a session key.  
     5. Server and client use the session key to encrypt further communication.

4. **How does HTTP/2 differ from HTTP/1.1?**  
   - **HTTP/1.1:** Sends requests sequentially; limited parallelism.  
   - **HTTP/2:**  
     - Uses multiplexing to send multiple requests over a single connection.  
     - Compresses headers for better performance.  
     - Allows server push to preemptively send data to the client.

5. **What is a WebSocket, and how does it differ from HTTP?**  
   - **WebSocket:** A protocol for full-duplex communication between a client and server over a single TCP connection.  
   - **Differences from HTTP:**
     - WebSocket maintains an open connection, whereas HTTP is stateless.  
     - WebSocket is ideal for real-time applications like chats and live updates.

6. **How do you secure an HTTP connection using HTTPS?**  
   - Install an SSL/TLS certificate on the server.  
   - Redirect HTTP requests to HTTPS using server configurations (e.g., `.htaccess` or Nginx).  
   - Enable HSTS to enforce HTTPS.  
   - Regularly update SSL/TLS versions and cipher suites.

7. **What is the purpose of HSTS (HTTP Strict Transport Security)?**  
   - HSTS is a security feature that enforces browsers to connect only via HTTPS.  
   - Prevents downgrade attacks and cookie hijacking.  
   - Implemented using the header: `Strict-Transport-Security: max-age=31536000; includeSubDomains`.

--- 

**AJAX:**

---

### **Basic Concepts**

1. **What is AJAX, and how does it work?**  
   - AJAX (Asynchronous JavaScript and XML) is a technique to send and retrieve data from a server asynchronously without refreshing the entire web page.  
   - **How it works:**  
     - A client-side script sends an asynchronous request using the `XMLHttpRequest` or `fetch` API.  
     - The server processes the request and sends a response.  
     - The client-side script updates the page dynamically based on the response.

2. **How is AJAX different from traditional web page requests?**  
   - Traditional web requests reload the entire page for every server interaction, while AJAX allows partial updates without reloading.  
   - AJAX enhances user experience with faster interactions and seamless page updates.

3. **What are the main advantages of using AJAX?**  
   - Improved user experience with partial page updates.  
   - Reduced server load by only transferring necessary data.  
   - Faster page interactions and better performance.  
   - Enables real-time features (e.g., live search, chat).

4. **Explain the role of the `XMLHttpRequest` object in AJAX.**  
   - `XMLHttpRequest` is a built-in browser object used to interact with servers via HTTP requests.  
   - It provides methods like `open()`, `send()`, and event listeners (`onload`, `onerror`) to manage requests and responses.

5. **Can AJAX requests be cached? If yes, how?**  
   - Yes, AJAX requests can be cached if the server sends appropriate cache headers (e.g., `Cache-Control`).  
   - **Client-side caching:** Add query parameters to avoid caching or use a service worker for better control.  
   - Example of avoiding caching: `url + "?nocache=" + new Date().getTime()`.

---

### **Implementation**

1. **Write a simple example of making an AJAX request in JavaScript.**  
   ```javascript
   const xhr = new XMLHttpRequest();
   xhr.open("GET", "https://api.example.com/data", true);
   xhr.onload = function () {
       if (xhr.status === 200) {
           console.log("Response:", JSON.parse(xhr.responseText));
       } else {
           console.error("Request failed with status:", xhr.status);
       }
   };
   xhr.onerror = function () {
       console.error("An error occurred during the request.");
   };
   xhr.send();
   ```

2. **How do you handle errors in AJAX?**  
   - Use the `onerror` event listener in `XMLHttpRequest` or `catch` for `fetch`.  
   - Check the HTTP status codes in the response.  
   - Implement retry logic or user-friendly error messages.

3. **What are the common HTTP methods used in AJAX, and when would you use each?**  
   - **GET:** Fetch data (e.g., `GET /products`).  
   - **POST:** Submit new data (e.g., `POST /add-user`).  
   - **PUT:** Update existing data (e.g., `PUT /update-user/123`).  
   - **DELETE:** Remove data (e.g., `DELETE /delete-user/123`).

4. **How can AJAX affect SEO?**  
   - AJAX content might not be indexed by search engines unless configured properly.  
   - Use techniques like server-side rendering (SSR) or dynamic rendering to make AJAX content accessible to search engine crawlers.

5. **Explain how AJAX can be used with JSON.**  
   - JSON (JavaScript Object Notation) is often used as a lightweight data format in AJAX responses.  
   - Example:  
     ```javascript
     const xhr = new XMLHttpRequest();
     xhr.open("GET", "https://api.example.com/data", true);
     xhr.onload = function () {
         const data = JSON.parse(xhr.responseText);
         console.log("Received JSON:", data);
     };
     xhr.send();
     ```

---

### **Advanced Topics**

1. **How do you debug AJAX requests in the browser?**  
   - Use browser developer tools (F12) to monitor network activity under the **Network** tab.  
   - Check request/response headers, status codes, and payload.  
   - Use console logs to trace errors and debugging tools like `console.table()` for better data visualization.

2. **What is the difference between synchronous and asynchronous AJAX calls?**  
   - **Synchronous:** Blocks the execution of code until the request is complete.  
     Example: `xhr.open("GET", url, false);`  
   - **Asynchronous:** Allows the code to continue execution while the request is being processed.  
     Example: `xhr.open("GET", url, true);` (default behavior).  

   - **Note:** Synchronous AJAX is deprecated due to its negative impact on user experience.

3. **How do you manage CORS issues in AJAX requests?**  
   - Ensure the server includes the appropriate CORS headers in its response:  
     - `Access-Control-Allow-Origin: *` (or specific domain).  
     - `Access-Control-Allow-Methods: GET, POST, OPTIONS`.  
   - Use preflight requests (`OPTIONS`) for complex requests.  
   - If possible, configure a reverse proxy to bypass CORS restrictions.  

---

