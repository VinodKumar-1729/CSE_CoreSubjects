### **JavaScript Interview Questions with Answers**

---

#### **1. What is JavaScript, and how is it different from Java?**
- **Answer:**
  - **JavaScript** is a lightweight, interpreted programming language primarily used for adding interactivity to web pages. It is dynamically typed and executed in a browser or server (Node.js).
  - **Java** is a statically typed, compiled programming language used for developing standalone, server-side, and web-based applications.
  - Key differences:
    - Java is class-based, while JavaScript is prototype-based.
    - JavaScript is executed in browsers, while Java requires a JVM.

---

#### **2. Explain the difference between `var`, `let`, and `const`.**
- **Answer:**
  - `var`: Function-scoped, hoisted, and can be redeclared.
  - `let`: Block-scoped, not hoisted, and cannot be redeclared in the same scope.
  - `const`: Block-scoped, not hoisted, and used for constants. The value cannot be reassigned.

---

#### **3. What are the data types available in JavaScript?**
- **Answer:**
  - **Primitive types:** `string`, `number`, `bigint`, `boolean`, `undefined`, `symbol`, and `null`.
  - **Non-primitive type:** `object` (includes arrays, functions, and objects).

---

#### **4. What is a closure in JavaScript? Provide an example.**
- **Answer:**
  - A **closure** is a function that has access to its own scope, the scope of the outer function, and the global scope even after the outer function has returned.
  - Example:
    ```javascript
    function outer() {
      let count = 0;
      return function inner() {
        count++;
        return count;
      };
    }
    const counter = outer();
    console.log(counter()); // 1
    console.log(counter()); // 2
    ```

---

#### **5. Explain the concept of "hoisting" in JavaScript.**
- **Answer:**
  - Hoisting is a JavaScript mechanism where variable and function declarations are moved to the top of their scope during the compile phase.
  - Example:
    ```javascript
    console.log(a); // undefined
    var a = 5;
    ```

---

#### **6. What are template literals, and how are they used?**
- **Answer:**
  - Template literals allow embedding expressions in strings using backticks (\``).
  - Example:
    ```javascript
    const name = "Vinod";
    console.log(`Hello, ${name}!`); // Hello, Vinod!
    ```

---

#### **7. What is the difference between `==` and `===`?**
- **Answer:**
  - `==`: Checks for equality after type coercion.
  - `===`: Checks for equality without type coercion.
  - Example:
    ```javascript
    console.log(5 == "5"); // true
    console.log(5 === "5"); // false
    ```

---

#### **8. What is the purpose of the `typeof` operator?**
- **Answer:**
  - `typeof` is used to determine the type of a variable.
  - Example:
    ```javascript
    console.log(typeof "Hello"); // string
    console.log(typeof 42); // number
    console.log(typeof null); // object
    ```

---

#### **9. What are JavaScript promises, and why are they used?**
- **Answer:**
  - A promise represents a value that may be available now, or in the future, or never. It is used for handling asynchronous operations.
  - Example:
    ```javascript
    const promise = new Promise((resolve, reject) => {
      setTimeout(() => resolve("Success!"), 1000);
    });
    promise.then(result => console.log(result)); // Success!
    ```

---

#### **10. Explain the difference between synchronous and asynchronous programming.**
- **Answer:**
  - **Synchronous**: Tasks are executed one at a time, blocking the execution of subsequent tasks.
  - **Asynchronous**: Tasks are executed without blocking, allowing other tasks to continue.

---

#### **11. What is an event loop in JavaScript, and how does it work?**
- **Answer:**
  - The event loop is a mechanism that manages the execution of asynchronous tasks in JavaScript by processing the callback queue after the call stack is empty.

---

#### **12. What is the difference between `null` and `undefined`?**
- **Answer:**
  - `null`: Explicitly assigned to indicate the absence of value.
  - `undefined`: Indicates a variable has been declared but not initialized.

---

#### **13. What are JavaScript objects, and how do you create them?**
- **Answer:**
  - JavaScript objects are collections of key-value pairs.
  - Example:
    ```javascript
    const obj = { name: "Vinod", age: 22 };
    ```

---

#### **14. What is the difference between deep copy and shallow copy?**
- **Answer:**
  - **Shallow copy** copies the reference to nested objects.
  - **Deep copy** creates a new copy of all nested objects.
  - Example:
    ```javascript
    const obj = { a: 1, b: { c: 2 } };
    const shallowCopy = { ...obj };
    const deepCopy = JSON.parse(JSON.stringify(obj));
    ```

---

#### **15. Explain the concept of prototypal inheritance.**
- **Answer:**
  - Objects inherit properties and methods from their prototype chain.
  - Example:
    ```javascript
    function Person(name) {
      this.name = name;
    }
    Person.prototype.greet = function () {
      return `Hello, ${this.name}`;
    };
    const vinod = new Person("Vinod");
    ```

---

#### **16. What are higher-order functions? Provide an example.**
- **Answer:**
  - Functions that take other functions as arguments or return functions.
  - Example:
    ```javascript
    const higherOrder = (fn) => fn();
    higherOrder(() => console.log("Hello")); // Hello
    ```

---

#### **17. What is the difference between `call()`, `apply()`, and `bind()`?**
- **Answer:**
  - `call()`: Calls a function with arguments passed individually.
  - `apply()`: Calls a function with arguments as an array.
  - `bind()`: Creates a new function with a specific `this` context.
  - Example:
    ```javascript
    const obj = { num: 2 };
    function multiply(x) { return this.num * x; }
    multiply.call(obj, 3); // 6
    multiply.apply(obj, [3]); // 6
    const boundFn = multiply.bind(obj);
    ```

---

#### **18. How is the `this` keyword used in JavaScript? Provide examples.**
- **Answer:**
  - `this` refers to the object that owns the function.
  - Example:
    ```javascript
    const obj = {
      name: "Vinod",
      greet() {
        return `Hello, ${this.name}`;
      },
    };
    ```

---

#### **19. What is the difference between an arrow function and a regular function?**
- **Answer:**
  - Arrow functions:
    - Do not have their own `this`.
    - Cannot be used as constructors.
  - Example:
    ```javascript
    const arrow = () => console.log("Arrow");
    ```

---

#### **20. Explain the `setTimeout` and `setInterval` functions.**
- **Answer:**
  - `setTimeout`: Executes a function after a delay.
  - `setInterval`: Repeatedly executes a function at intervals.
  - Example:
    ```javascript
    setTimeout(() => console.log("Timeout"), 1000);
    setInterval(() => console.log("Interval"), 1000);
    ```

---

#### **21. What are JavaScript modules? Explain `export` and `import`.**
- **Answer:**
  - Modules allow code to be split into reusable files.
  - Example:
    ```javascript
    // file1.js
    export const greet = () => console.log("Hello");
    // file2.js
    import { greet } from "./file1";
    ```

--- 

### **Intermediate JavaScript Interview Questions with Answers**

---

#### **1. What are ES6 features? Name a few and explain them.**

- **Answer:**
  ES6 (ECMAScript 2015) introduced significant improvements to JavaScript. Key features include:
  - **`let` and `const`:** Block-scoped variable declarations.
  - **Arrow functions:** Concise syntax for writing functions without their own `this`.
    ```javascript
    const add = (a, b) => a + b;
    ```
  - **Template literals:** String interpolation using backticks.
    ```javascript
    const name = "Vinod";
    console.log(`Hello, ${name}!`);
    ```
  - **Destructuring:** Unpacking arrays or objects.
    ```javascript
    const [a, b] = [1, 2];
    const { name } = { name: "Vinod", age: 22 };
    ```
  - **Default parameters:** Setting default values for function parameters.
    ```javascript
    function greet(name = "Guest") {
      return `Hello, ${name}`;
    }
    ```
  - **Promises:** Handling asynchronous code.
  - **Modules:** `import` and `export` for modular code.

---

#### **2. How does the `async` and `await` syntax work in JavaScript?**

- **Answer:**
  - `async` and `await` simplify working with promises, allowing asynchronous code to be written like synchronous code.
  - **`async` function:** Always returns a promise.
  - **`await`:** Pauses the execution of the function until the promise resolves.
  - Example:
    ```javascript
    async function fetchData() {
      try {
        const response = await fetch("https://api.example.com/data");
        const data = await response.json();
        console.log(data);
      } catch (error) {
        console.error("Error:", error);
      }
    }
    ```

---

#### **3. What is event delegation in JavaScript? Provide an example.**

- **Answer:**
  - Event delegation leverages the event bubbling mechanism to handle events efficiently. Instead of attaching listeners to individual child elements, a listener is attached to a common parent.
  - Example:
    ```javascript
    document.getElementById("parent").addEventListener("click", function (event) {
      if (event.target.tagName === "BUTTON") {
        console.log("Button clicked:", event.target.textContent);
      }
    });
    ```

---

#### **4. What is the difference between local storage, session storage, and cookies?**

- **Answer:**
  - **Local Storage:**
    - Stores data with no expiration.
    - Accessible only on the same origin.
    - Max size: ~5MB.
  - **Session Storage:**
    - Stores data for the duration of a page session (until the browser/tab is closed).
    - Max size: ~5MB.
  - **Cookies:**
    - Stores small pieces of data (4KB) sent with every HTTP request.
    - Can have an expiration time.
    - Can be used for server communication.

---

#### **5. How does the `reduce()` function work in JavaScript?**

- **Answer:**
  - `reduce()` applies a reducer function to each element of an array to accumulate a single output value.
  - Syntax:
    ```javascript
    array.reduce((accumulator, currentValue) => {
      // logic
    }, initialValue);
    ```
  - Example:
    ```javascript
    const numbers = [1, 2, 3, 4];
    const sum = numbers.reduce((acc, num) => acc + num, 0);
    console.log(sum); // 10
    ```

---

#### **6. What are JavaScript classes? How are they different from functions?**

- **Answer:**
  - **Classes:** Introduced in ES6 as syntactic sugar over constructor functions for creating objects and managing inheritance.
    ```javascript
    class Person {
      constructor(name) {
        this.name = name;
      }
      greet() {
        return `Hello, ${this.name}`;
      }
    }
    const vinod = new Person("Vinod");
    console.log(vinod.greet());
    ```
  - **Differences from functions:**
    - Classes cannot be called without `new`.
    - Class methods are not enumerable.
    - Inheritance is easier with `extends`.

---

#### **7. Explain the concept of immutability in JavaScript.**

- **Answer:**
  - **Immutability** means that the state of an object or data structure cannot be changed after it is created. Instead, new objects are created.
  - Benefits:
    - Predictable state management.
    - Avoids side effects.
  - Example:
    ```javascript
    const arr = [1, 2, 3];
    const newArr = [...arr, 4]; // Original array remains unchanged
    ```

---

#### **8. What are JavaScript generators? How do they differ from regular functions?**

- **Answer:**
  - A generator is a special type of function that can pause and resume execution using `yield`.
  - **Key differences:**
    - Regular functions execute completely when called.
    - Generators return an iterator and can pause execution using `yield`.
  - Example:
    ```javascript
    function* generator() {
      yield 1;
      yield 2;
      yield 3;
    }
    const gen = generator();
    console.log(gen.next().value); // 1
    console.log(gen.next().value); // 2
    ```

---

#### **9. What is the difference between `for...of` and `for...in` loops?**

- **Answer:**
  - **`for...of`:**
    - Iterates over iterable objects (like arrays, strings).
    - Accesses **values**.
    - Example:
      ```javascript
      const arr = [1, 2, 3];
      for (const value of arr) {
        console.log(value); // 1, 2, 3
      }
      ```
  - **`for...in`:**
    - Iterates over enumerable properties of an object.
    - Accesses **keys**.
    - Example:
      ```javascript
      const obj = { a: 1, b: 2 };
      for (const key in obj) {
        console.log(key); // a, b
      }
      ```

---

#### **10. What is the `Symbol` data type in JavaScript?**

- **Answer:**
  - `Symbol` is a unique and immutable primitive value used as object property keys to avoid name collisions.
  - Example:
    ```javascript
    const sym = Symbol("description");
    const obj = { [sym]: "value" };
    console.log(obj[sym]); // value
    ```

--- 

