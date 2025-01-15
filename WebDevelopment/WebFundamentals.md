

### **1. HTTP/HTTPS**
**HTTP (Hypertext Transfer Protocol):**
- **Definition:** HTTP is an application-layer protocol used for transmitting hypertext over the web. It is stateless and operates on the client-server model.
- **Key Features:**
  - **Methods:** GET, POST, PUT, DELETE, PATCH, OPTIONS, HEAD, TRACE, CONNECT.
  - **Stateless Protocol:** Each request is independent and has no memory of previous interactions.
  - **Port Number:** HTTP typically uses port 80.
- **Common Headers:** 
  - Request Headers: `Host`, `User-Agent`, `Authorization`, `Accept`.
  - Response Headers: `Content-Type`, `Set-Cookie`, `Cache-Control`.

**HTTPS (HTTP Secure):**
- **Definition:** HTTPS is the secure version of HTTP. It encrypts communication using SSL/TLS.
- **Key Features:**
  - **Encryption:** Ensures data integrity and confidentiality.
  - **Authentication:** Verifies the server identity using certificates.
  - **Port Number:** HTTPS typically uses port 443.
- **Advantages of HTTPS:**
  - Protects against man-in-the-middle attacks.
  - Improves trustworthiness and SEO ranking.

---

### **2. AJAX (Asynchronous JavaScript and XML)**
**Definition:** AJAX is a technique for creating dynamic and asynchronous web applications, enabling partial page updates without refreshing the entire page.

**Key Features:**
- **Asynchronous Communication:** Allows sending and receiving data in the background.
- **XMLHttpRequest (XHR):** The object used for making AJAX calls.
- **Supported Data Formats:** XML, JSON, HTML, or plain text.

**Common AJAX Methods:**
1. **Create XHR Object:**
   ```javascript
   const xhr = new XMLHttpRequest();
   ```
2. **Open Connection:**
   ```javascript
   xhr.open('GET', 'url', true);
   ```
3. **Send Request:**
   ```javascript
   xhr.send();
   ```
4. **Handle Response:**
   ```javascript
   xhr.onreadystatechange = () => {
       if (xhr.readyState === 4 && xhr.status === 200) {
           console.log(xhr.responseText);
       }
   };
   ```

**Advantages:**
- Faster updates.
- Reduced server load.
- Enhanced user experience.

---

### **3. REST APIs (GET, POST, PUT, DELETE)**
**Definition:** REST (Representational State Transfer) is an architectural style for designing networked applications. It uses standard HTTP methods for CRUD operations.

**Key Features:**
- **Statelessness:** Each API call is independent.
- **Resource Identification:** Each resource is uniquely identified using a URI.

**HTTP Methods:**
1. **GET:** Retrieve data.
   - Example: Fetching user details.
   ```bash
   GET /users/1
   ```
2. **POST:** Create new data.
   - Example: Creating a new user.
   ```bash
   POST /users
   Body: { "name": "John", "email": "john@example.com" }
   ```
3. **PUT:** Update existing data.
   - Example: Updating user details.
   ```bash
   PUT /users/1
   Body: { "name": "John Doe" }
   ```
4. **DELETE:** Delete a resource.
   - Example: Removing a user.
   ```bash
   DELETE /users/1
   ```

**REST Principles:**
- Uniform Interface.
- Stateless Communication.
- Cacheable Responses.

---

### **4. Cookies**
**Definition:** Cookies are small text files stored on the user's device by a web browser. They are used to remember user information.

**Types of Cookies:**
1. **Session Cookies:** Temporary, deleted after the session ends.
2. **Persistent Cookies:** Stored until they expire or are manually deleted.
3. **Secure Cookies:** Transmitted only over HTTPS.
4. **HttpOnly Cookies:** Not accessible via JavaScript, enhancing security.

**Attributes:**
- `Domain`: Specifies the domain for the cookie.
- `Path`: Limits where the cookie is sent.
- `Expires/Max-Age`: Determines the cookie's lifespan.
- `Secure`: Ensures cookies are sent only over HTTPS.
- `HttpOnly`: Prevents JavaScript access.

**Example in JavaScript:**
```javascript
// Set a cookie
document.cookie = "username=Vinod; path=/; expires=Fri, 31 Dec 2025 23:59:59 GMT";
// Get cookies
console.log(document.cookie);
```

---

### **5. Version Control Systems (Git)**
**Definition:** A version control system (VCS) tracks changes to files, allowing multiple people to collaborate on a project and revert to previous versions if needed.

**Git:**
- **Definition:** Git is a distributed version control system.
- **Advantages:**
  - Tracks history of changes.
  - Facilitates collaboration through branching and merging.
  - Works offline for local repositories.

**Common Commands:**
1. **Initialize Repository:**
   ```bash
   git init
   ```
2. **Clone Repository:**
   ```bash
   git clone <repository-url>
   ```
3. **Check Status:**
   ```bash
   git status
   ```
4. **Stage Changes:**
   ```bash
   git add <file>
   ```
5. **Commit Changes:**
   ```bash
   git commit -m "Commit message"
   ```
6. **Push to Remote Repository:**
   ```bash
   git push origin <branch-name>
   ```
7. **Pull Latest Changes:**
   ```bash
   git pull
   ```

**Branching and Merging:**
- **Create a New Branch:**
  ```bash
  git branch <branch-name>
  ```
- **Switch Branch:**
  ```bash
  git checkout <branch-name>
  ```
- **Merge Branch:**
  ```bash
  git merge <branch-name>
  ```

**Git Workflow:**
1. Create or clone a repository.
2. Make changes locally.
3. Stage and commit changes.
4. Push changes to a remote repository.

---
