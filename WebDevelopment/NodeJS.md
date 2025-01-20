### **NodeJS Interview Questions with Answers**

---

### **Basics**

---

#### **1. What is NodeJS, and what are its primary use cases?**  
- **Answer:**  
  NodeJS is an open-source, cross-platform runtime environment for executing JavaScript code outside the browser.  
  **Primary Use Cases:**  
  - Building scalable network applications.  
  - Creating APIs and microservices.  
  - Real-time applications like chat and gaming apps.  
  - File streaming services.  

---

#### **2. What is the difference between NodeJS and JavaScript?**  
- **Answer:**  
  - **JavaScript:** A programming language used for web development.  
  - **NodeJS:** A runtime environment for executing JavaScript on the server side.  

---

#### **3. What are the main features of NodeJS?**  
- **Answer:**  
  - **Non-blocking I/O:** Handles concurrent requests efficiently.  
  - **Single-threaded event loop:** Uses a single thread for asynchronous processing.  
  - **Cross-platform:** Runs on multiple operating systems.  
  - **Package management with NPM:** Access to a rich library of modules.  

---

#### **4. What is the difference between `require()` and `import`?**  
- **Answer:**  
  - **`require()`:** CommonJS syntax, used in NodeJS.  
  - **`import`:** ES6 syntax, used in modern JavaScript.  
  - Example:  
    ```javascript
    // CommonJS
    const fs = require('fs');
    // ES6
    import fs from 'fs';
    ```

---

#### **5. What is NPM, and how does it work?**  
- **Answer:**  
  NPM (Node Package Manager) is a tool for managing packages in NodeJS.  
  - Install a package: `npm install package-name`.  
  - Initialize a project: `npm init`.  

---

#### **6. What is the purpose of the `fs` module in NodeJS?**  
- **Answer:**  
  The `fs` module handles file operations like reading, writing, and deleting files.  
  Example:
  ```javascript
  const fs = require('fs');
  fs.readFile('file.txt', 'utf8', (err, data) => {
    if (err) throw err;
    console.log(data);
  });
  ```

---

#### **7. What are streams in NodeJS? Explain their types.**  
- **Answer:**  
  Streams are used for reading or writing data sequentially.  
  **Types:**  
  - **Readable:** Stream for reading data.  
  - **Writable:** Stream for writing data.  
  - **Duplex:** Stream for both reading and writing.  
  - **Transform:** Duplex stream that modifies data during reading/writing.  

---

#### **8. What is middleware in NodeJS?**  
- **Answer:**  
  Middleware functions process requests and responses in an Express application.  
  Example:  
  ```javascript
  app.use((req, res, next) => {
    console.log('Middleware executed');
    next();
  });
  ```

---

#### **9. What is the difference between synchronous and asynchronous methods in NodeJS?**  
- **Answer:**  
  - **Synchronous:** Blocks the execution until the task completes.  
  - **Asynchronous:** Uses callbacks, promises, or async/await to handle tasks without blocking execution.  

---

#### **10. How does NodeJS handle multiple requests on a single-threaded architecture?**  
- **Answer:**  
  NodeJS uses an **event loop** to handle multiple requests asynchronously, delegating tasks like I/O to worker threads.

---

### **Intermediate**

---

#### **1. What is the Event Loop in NodeJS, and how does it work?**  
- **Answer:**  
  The event loop processes asynchronous callbacks in phases:  
  - **Timers:** Executes `setTimeout` and `setInterval`.  
  - **Pending callbacks:** Executes I/O callbacks.  
  - **Idle, prepare:** Used internally.  
  - **Poll:** Retrieves new I/O events.  
  - **Check:** Executes `setImmediate` callbacks.  
  - **Close callbacks:** Executes close events like `socket.on('close')`.

---

#### **2. Explain the difference between `process.nextTick()` and `setImmediate()`.**  
- **Answer:**  
  - **`process.nextTick()`:** Executes callbacks before the next event loop iteration.  
  - **`setImmediate()`:** Executes callbacks in the `check` phase of the event loop.

---

#### **3. How is the Express framework used in NodeJS?**  
- **Answer:**  
  Express is used for building web applications and APIs.  
  Example:
  ```javascript
  const express = require('express');
  const app = express();
  app.get('/', (req, res) => res.send('Hello World!'));
  app.listen(3000);
  ```

---

#### **4. What is CORS, and how do you handle it in NodeJS?**  
- **Answer:**  
  - **CORS (Cross-Origin Resource Sharing):** Controls resource sharing between different origins.  
  - Handled using the `cors` package:  
    ```javascript
    const cors = require('cors');
    app.use(cors());
    ```

---

#### **5. What are REST APIs, and how do you create one using Express?**  
- **Answer:**  
  REST APIs are web services that adhere to REST architecture.  
  Example:
  ```javascript
  app.get('/api/data', (req, res) => res.json({ message: 'Hello World' }));
  ```

---

#### **6. What is the purpose of the `path` module in NodeJS?**  
- **Answer:**  
  The `path` module provides utilities for working with file and directory paths.  
  Example:
  ```javascript
  const path = require('path');
  const dir = path.join(__dirname, 'folder');
  ```

---

#### **7. What is a buffer in NodeJS, and why is it used?**  
- **Answer:**  
  Buffers handle binary data in NodeJS. Useful for file I/O operations.  
  Example:
  ```javascript
  const buf = Buffer.from('Hello');
  console.log(buf.toString());
  ```

---

#### **8. How do you handle errors in NodeJS?**  
- **Answer:**  
  Use `try...catch`, error callbacks, or middleware.  
  Example:
  ```javascript
  app.use((err, req, res, next) => {
    console.error(err.stack);
    res.status(500).send('Something broke!');
  });
  ```

---

#### **9. What is the difference between a callback, a promise, and async/await in NodeJS?**  
- **Answer:**  
  - **Callback:** A function passed as an argument to be executed later.  
  - **Promise:** Represents the eventual result of an asynchronous operation.  
  - **Async/await:** Simplifies promises for cleaner syntax.  

---

#### **10. What is clustering in NodeJS, and how does it improve performance?**  
- **Answer:**  
  - Clustering creates child processes to utilize multiple CPU cores.  
  - Example:
    ```javascript
    const cluster = require('cluster');
    const http = require('http');
    if (cluster.isMaster) {
      cluster.fork();
    } else {
      http.createServer((req, res) => res.end('Hello World')).listen(8000);
    }
    ```

--- 
