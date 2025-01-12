


### **HTTP/HTTPS**
**HTTP (HyperText Transfer Protocol):**  
- **Purpose:** A stateless protocol used for transferring data between a client (browser) and a server.  
- **Working:**  
  1. A client sends an HTTP request to a server.  
  2. The server processes the request and sends back an HTTP response with data.  
- **Methods:**
  - **GET:** Retrieve data from the server (e.g., fetching a webpage).
  - **POST:** Send data to the server (e.g., submitting a form).
  - **PUT:** Update existing resources on the server.
  - **DELETE:** Remove a resource from the server.  
- **Status Codes:** Indicate the outcome of a request:
  - 2xx: Success (e.g., 200 OK).
  - 4xx: Client errors (e.g., 404 Not Found).
  - 5xx: Server errors (e.g., 500 Internal Server Error).  

**HTTPS (HTTP Secure):**  
- An extension of HTTP that uses **SSL/TLS** for encryption, ensuring secure data transmission.
- **Key Features:**
  - Encrypts communication to prevent data theft (man-in-the-middle attacks).
  - Authenticates the server’s identity using digital certificates (e.g., provided by a Certificate Authority).
  - Common in websites handling sensitive information (e.g., banking, e-commerce).

---

### **AJAX (Asynchronous JavaScript and XML)**
**Definition:** A technique that allows web pages to update content dynamically without requiring a full-page reload.  

**How It Works:**  
1. An event triggers an AJAX request (e.g., clicking a button).  
2. JavaScript sends an asynchronous request to the server using the `XMLHttpRequest` object or modern `fetch` API.  
3. The server processes the request and sends back data (often in JSON format).  
4. The browser updates the webpage content based on the response.  

**Advantages:**  
- Faster updates as only parts of the page are refreshed.
- Improved user experience with real-time data.

**Example Code (AJAX with Fetch API):**
```javascript
fetch('https://api.example.com/data')
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

**Applications:**  
- Real-time search suggestions (e.g., Google autocomplete).  
- Infinite scrolling (e.g., social media feeds).  

---

### **REST APIs (GET, POST, PUT, DELETE)**  
**Definition:** Representational State Transfer (REST) APIs allow communication between systems over HTTP using predefined methods.

**Key Concepts:**
- **Stateless:** Each request is independent and does not rely on previous requests.
- **Resources:** Represented as URLs (e.g., `/users` for user data).
- **HTTP Methods:**
  - **GET:** Retrieve resources.
  - **POST:** Create new resources.
  - **PUT:** Update existing resources (replaces the resource).
  - **DELETE:** Remove resources.

**Example:**
- **GET /users:** Fetch all users.
- **POST /users:** Add a new user.
- **PUT /users/123:** Update user with ID 123.
- **DELETE /users/123:** Delete user with ID 123.

**Best Practices:**
- Use meaningful endpoints (e.g., `/products` instead of `/getProducts`).
- Return appropriate HTTP status codes (e.g., `201 Created` for successful POST).

---

### **Cookies**
**Definition:** Small pieces of data stored in a user’s browser, often used to track user activity, maintain sessions, or store preferences.  

**Types of Cookies:**
1. **Session Cookies:** Temporary, deleted after the session ends.
2. **Persistent Cookies:** Stored for a defined duration.
3. **Secure Cookies:** Transmitted only over HTTPS.
4. **HttpOnly Cookies:** Accessible only via server-side code (not JavaScript).

**Attributes:**
- `Secure`: Ensures cookies are sent only over HTTPS.
- `HttpOnly`: Prevents client-side scripts from accessing the cookie.
- `SameSite`: Protects against CSRF by restricting cross-site requests.

**Usage:**
- Authentication (e.g., session IDs).
- User preferences (e.g., dark mode setting).

**Example Code:**
```javascript
document.cookie = "username=Vinod; path=/; Secure; HttpOnly";
```

---

### **Version Control Systems (Git)**
**Definition:** A tool used to manage and track changes in source code over time. Git is the most popular version control system.  

**Key Features:**
- **Local Repository:** Each developer has a complete copy of the codebase.
- **Tracking Changes:** Tracks additions, deletions, and modifications.
- **Branching and Merging:**
  - Branching allows you to work on features or fixes independently.
  - Merging integrates changes from different branches.

**Common Commands:**
- `git init`: Initialize a new repository.
- `git add <file>`: Stage changes for commit.
- `git commit -m "<message>"`: Save changes to the repository.
- `git branch`: List branches.
- `git checkout <branch>`: Switch branches.
- `git push`: Upload local changes to a remote repository.
- `git pull`: Fetch and merge changes from a remote repository.

**Benefits:**
- Collaboration: Multiple developers can work on the same project.
- Rollbacks: Easily revert to previous versions.
- Code Quality: Allows peer review through pull requests.

---
