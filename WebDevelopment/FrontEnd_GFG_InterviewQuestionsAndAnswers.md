1. **What is HTML?**
   - HTML stands for HyperText Markup Language. It is used to define the structure of web pages with the help of various tags.

2. **What are Semantic elements in HTML?**
   - Semantic elements clearly describe their meaning in a way that is understandable by both developers and browsers. Examples include:
     - `<header>`
     - `<main>`
     - `<section>`
     - `<article>`
     - `<aside>`
     - `<footer>`

3. **What are Empty elements in HTML?**
   - Empty elements do not require a closing tag. These are also called self-closing elements. Examples: `<img>`, `<input>`, `<br>`, `<hr>`.

4. **Differentiate between Inline and Block elements in HTML.**
   - **Inline elements:**
     - Do not start on a new line.
     - Take only as much width as necessary.
     - Examples: `<a>`, `<strong>`, `<img>`.
   - **Block elements:**
     - Always start on a new line.
     - Take up the full width available.
     - Examples: `<div>`, `<h1>` to `<h6>`, `<p>`.

5. **What is a list in HTML? Explain different types of lists.**
   - Lists are used to display a collection of items. Types include:
     1. **Unordered List:** Items are displayed with bullets. Defined using `<ul>` and `<li>`.
        ```html
        <ul>
            <li>Item 1</li>
            <li>Item 2</li>
        </ul>
        ```
     2. **Ordered List:** Items are displayed with numbers. Defined using `<ol>` and `<li>`.
        ```html
        <ol>
            <li>Item 1</li>
            <li>Item 2</li>
        </ol>
        ```
     3. **Definition List:** Contains terms and their definitions. Defined using `<dl>`, `<dt>`, and `<dd>`.
        ```html
        <dl>
            <dt>Term 1</dt>
            <dd>Definition 1</dd>
        </dl>
        ```

6. **What is the basic structure of an HTML document?**
   ```html
   <!DOCTYPE html>
   <html lang="en">
       <head>
           <title>Document</title>
       </head>
       <body></body>
   </html>
   ```

7. **Explain the elements in the basic structure of an HTML document.**
   - `<!DOCTYPE html>`: Declares the document type as HTML5.
   - `<html>`: Root element of the HTML document.
   - `<head>`: Contains metadata such as title and links.
   - `<title>`: Specifies the title of the document, displayed in the browser tab.
   - `<body>`: Contains the visible content of the web page.

8. **What are HTML tags?**
   - HTML tags define elements on a web page. They are enclosed within angle brackets (e.g., `<div>`, `<p>`).

9. **Why is the `alt` attribute used with the `<img>` tag?**
   - The `alt` attribute provides alternative text for an image. It is displayed if the image fails to load and improves accessibility.

10. **What is the difference between `<div>` and `<span>`?**
    - `<div>`:
      - Block-level element.
      - Used for grouping larger sections.
    - `<span>`:
      - Inline element.
      - Used for styling small parts of content.

11. **Why is the `<meta charset="UTF-8">` tag used?**
    - It specifies the character encoding as UTF-8 to properly display text and special characters.

12. **What is the purpose of the `role` attribute in HTML?**
    - The `role` attribute defines an element’s purpose, enhancing accessibility for assistive technologies like screen readers.

13. **Differentiate between the GET and POST methods in HTML forms.**
    - **GET Method:**
      - Data is sent via URL.
      - Less secure.
      - Suitable for non-sensitive data.
    - **POST Method:**
      - Data is sent in the request body.
      - More secure.
      - Suitable for sensitive data.

14. **What is the use of the `<iframe>` tag?**
    - The `<iframe>` tag embeds external content (e.g., videos, maps) within a web page.

15. **Explain the features of HTML5.**
    - New semantic elements: `<header>`, `<footer>`, `<nav>`.
    - New form inputs: `email`, `number`, `date`.
    - Multimedia support: `<audio>` and `<video>`.
    - `<canvas>` for graphics.
    - Browser storage: `localStorage` and `sessionStorage`.

16. **What is localStorage?**
    - `localStorage` allows data storage in key-value pairs that persist even after the browser is closed.

17. **What is sessionStorage?**
    - `sessionStorage` stores data temporarily and is cleared when the browser tab or window is closed.

18. **Differentiate between localStorage and sessionStorage.**
    - **localStorage:**
      - Data persists across sessions.
      - Accessible in all tabs of the browser.
    - **sessionStorage:**
      - Data is cleared when the session ends.
      - Accessible only in the current tab.

19. **What is the purpose of `<figure>` and `<figcaption>`?**
    - `<figure>`: Groups media elements (images, videos).
    - `<figcaption>`: Provides captions or descriptions for `<figure>` content.

20. **Write the HTML code to create a table with 3 columns and 3 rows.**
    ```html
    <table border="1">
        <thead>
            <tr>
                <th>Col 1</th>
                <th>Col 2</th>
                <th>Col 3</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>Row 1, Col 1</td>
                <td>Row 1, Col 2</td>
                <td>Row 1, Col 3</td>
            </tr>
            <tr>
                <td>Row 2, Col 1</td>
                <td>Row 2, Col 2</td>
                <td>Row 2, Col 3</td>
            </tr>
        </tbody>
    </table>
    ```

21. **How can you merge rows and columns in an HTML table?**
    - Use `colspan` to merge columns and `rowspan` to merge rows.

22. **What are data attributes in HTML?**
    - Data attributes (`data-*`) store custom data for HTML elements. These can be accessed via JavaScript but should be used cautiously as they can be modified easily through browser tools.

### CSS Notes

**23. What is CSS?**
CSS stands for Cascading Style Sheets. It is used to style and design web pages to make them visually appealing. CSS provides various selectors to target HTML elements and style them as needed. Common selectors include element selectors, class selectors, and ID selectors.

---

**24. Explain selectors in CSS.**
Selectors in CSS are used to target HTML elements and apply styles. Common types include:

1. **Element Selector**: Targets elements by their name (e.g., `div`).
2. **ID Selector**: Targets elements with a specific `id` using `#` (e.g., `#header`).
3. **Class Selector**: Targets elements with a specific `class` using `.` (e.g., `.btn`).
4. **Universal Selector**: Targets all elements using `*`.
5. **Attribute Selector**: Targets elements based on attributes (e.g., `input[type="text"]`).
6. **Child Selector**: Targets direct child elements using `>` (e.g., `div > p`).
7. **Pseudo-Selectors**: Target specific states or parts of elements (e.g., `:hover`, `:nth-child()`).

---

**25. Explain the precedence of class, ID, and element selectors in CSS.**
The order of precedence is:

1. ID Selector (`#id`) > Class Selector (`.class`) > Element Selector (`element`).
2. Combination of selectors increases specificity (e.g., `#id.class` > `#id.element` > `.class.element`).

---

**26. What are the best practices for using JavaScript and CSS?**
Some best practices include:

1. Use external files for CSS (`.css`) and JavaScript (`.js`).
2. Link CSS files in the `<head>` section.
3. Place JavaScript files just before the closing `</body>` tag for better performance.
4. Use meaningful variable names and avoid global variables in JavaScript.
5. Write CSS and JavaScript in a clean and structured way to avoid conflicts.

---

**27. What is the difference between `visibility: hidden` and `display: none`?**
- **`visibility: hidden`**: Hides the element but retains its space in the layout.
- **`display: none`**: Hides the element and removes it from the layout, freeing up the space.

---

**28. Mention issues faced by developers when running CSS in Internet Explorer (IE).**
Common issues include:

1. Transparency problems with `.png` images.
2. Misinterpretation of the `z-index` property.
3. Margin doubling issues.
4. Differences in the box model interpretation.
5. Limited support for modern CSS3 features.

---

**29. Explain the box model in CSS.**
The CSS box model describes how elements are structured:

1. **Content**: The content inside the element.
2. **Padding**: Space between content and the border.
3. **Border**: Surrounds the padding and content.
4. **Margin**: Space outside the border, separating the element from others.

---

**30. What is the purpose of the `z-index` property in CSS?**
The `z-index` property determines the stacking order of elements. Higher values bring elements to the front, while lower or negative values move them behind other elements.

---

**31. What is the use of the `float` property?**
The `float` property is used to position elements to the left or right of their container. It is commonly used for layouts, allowing text or other elements to wrap around floated items.

---

**32. Explain different ways to center an element on a webpage.**
Common methods include:

1. **Margin Auto**: `margin: 0 auto;` for horizontal centering.
2. **Flexbox**: Use `display: flex; align-items: center; justify-content: center;`.
3. **Position and Transform**: Use `position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%);`.

---

**33. Describe the use of the `position` property in CSS.**
The `position` property specifies how an element is positioned in the document. Values include:

1. **Static**: Default position (no special positioning).
2. **Relative**: Positioned relative to its normal position.
3. **Absolute**: Positioned relative to its nearest positioned ancestor.
4. **Fixed**: Positioned relative to the viewport.
5. **Sticky**: Toggles between `relative` and `fixed` based on scroll position.

---

**34. What are pseudo-classes and pseudo-elements in CSS?**
- **Pseudo-Classes**: Target specific states of an element (e.g., `:hover`, `:focus`).
- **Pseudo-Elements**: Style specific parts of an element (e.g., `::before`, `::after`).

---

**35. Why is `!important` used in CSS?**
The `!important` declaration is used to give a CSS rule higher priority, overriding any other conflicting rules for the same property.

---

**36. What is the purpose of the `box-sizing` property?**
The `box-sizing` property controls how the total width and height of an element are calculated. Common values include:

1. **Content-box**: Default; excludes padding and border from the dimensions.
2. **Border-box**: Includes padding and border in the dimensions.

---

**37. What are CSS preprocessors, and what are their advantages?**
CSS preprocessors like SASS and LESS extend CSS by adding features like variables, nesting, and mixins. Advantages:

1. Improved maintainability.
2. Reduced code duplication.
3. Easier implementation of complex styles.

---

**38. What does "Cascading" mean in Cascading Style Sheets?**
"Cascading" refers to the order of priority for applying styles. The hierarchy is:

1. User-defined styles.
2. Author-defined styles.
3. Default browser styles.

---

**39. Explain media queries in CSS.**
Media queries are used to apply styles based on the device's width, height, or other properties. They are commonly used for creating responsive designs. Example:

```css
@media (max-width: 768px) {
  body {
    background-color: lightblue;
  }
}
```

---

**40. Describe CSS sprites and their importance.**
CSS sprites combine multiple images into one file. The `background-position` property is used to display specific parts of the sprite. This technique reduces server requests, improving website performance.

---

**41. How can you optimize CSS file loading in the browser?**
To optimize CSS loading:

1. Minimize the number of CSS files.
2. Minify CSS to reduce file size.
3. Leverage browser caching.
4. Load unnecessary styles asynchronously or defer their loading.

---

**42. How can you create responsive designs?**
Key techniques for responsive designs include:

1. Using media queries.
2. Employing flexbox and grid layouts.
3. Using relative units like percentages, `vh`, and `vw`.
4. Avoiding fixed-width elements and ensuring content adjusts dynamically to screen sizes.


### JavaScript Notes

**43. What is JavaScript?**
JavaScript is a high-level, interpreted scripting language that is dynamically typed. It is used to add interactivity, dynamic elements, and styles to web pages, making them more engaging and functional. JavaScript can be used for both frontend (e.g., ReactJS, Vue.js, Angular) and backend development (using Node.js).

---

**44. What is the difference between == and === in JavaScript?**
- `==` (double equals): Compares values for equality after performing type conversion if necessary.
  - Example: `3 == "3" // true`
- `===` (triple equals): Compares values and types for strict equality.
  - Example: `3 === "3" // false`

---

**45. How to defer an element’s event handler if it depends on an external script that takes time to load?**
Use the `defer` attribute in the `<script>` tag to ensure the script is executed only after the HTML is fully parsed. Then dynamically attach the event handler once the external script is confirmed to be loaded:

```html
<script src="external-script.js" defer></script>
```

```javascript
document.addEventListener('DOMContentLoaded', function() {
    if (typeof externalFunction === "function") {
        const button = document.getElementById('myButton');
        button.addEventListener('click', externalFunction);
    }
});
```

---

**46. What is the optimal strategy for winning a game where the goal is to say 100 first?**
Ensure your opponent is left with numbers where they cannot avoid making 100 available for you. Start with numbers like 89, 78, 67, and so on—leaving the opponent with a range that inevitably leads to you saying 100.

---

**47. Why would you use prototypes in JavaScript?**
Prototypes in JavaScript are used to:
1. Share methods across all instances of an object, saving memory.
2. Implement inheritance.
3. Dynamically add properties or methods to objects.

---

**48. What does the ‘this’ keyword mean in JavaScript?**
The `this` keyword refers to the object that is executing the current function. Its value depends on how the function is called:
- In a global context, `this` refers to the global object (e.g., `window` in browsers).
- Inside an object’s method, `this` refers to that object.
- In a function, `this` depends on how the function is invoked.

Example:
```javascript
const obj = {
    name: "Example",
    greet() {
        console.log(this.name);
    }
};
obj.greet(); // "Example"
```

---

**49. What are namespaces in JavaScript?**
Namespaces help encapsulate variables and functions to avoid conflicts in a program. Objects are often used as namespaces.

Example:
```javascript
const MyNamespace = {
    data: 42,
    display() {
        console.log(this.data);
    }
};
MyNamespace.display();
```

---

**50. Difference between `null` and `undefined` in JavaScript.**
- `undefined`: A variable is declared but not assigned a value.
- `null`: Represents an intentional absence of any value.

Example:
```javascript
let a; // undefined
let b = null; // null
```

---

**51. Explain closures in JavaScript with an example.**
A closure is when an inner function retains access to the variables of its outer function even after the outer function has returned.

Example:
```javascript
function createCounter() {
    let count = 0;
    return function () {
        count++;
        return count;
    };
}
const counter = createCounter();
console.log(counter()); // 1
console.log(counter()); // 2
```

---

**52. What is the event loop in JavaScript?**
The event loop handles asynchronous operations in JavaScript. It continuously checks the call stack and callback queue. When the call stack is empty, it pushes queued callbacks to the stack for execution.

---

**53. Explain hoisting in JavaScript.**
Hoisting allows variables and functions to be used before they are declared. Variables declared with `var` are hoisted but initialized to `undefined`, whereas `let` and `const` are hoisted but not initialized.

Example:
```javascript
console.log(a); // undefined
var a = 10;
```

---

**54. What are the data types in JavaScript?**
- **Primitive**: `string`, `number`, `boolean`, `null`, `undefined`, `BigInt`, `symbol`.
- **Non-Primitive**: Objects (including arrays, functions).

---

**55. If `typeof([])` is object, what is the content and length of `b` in this code?**
```javascript
let b = [];
b.v = 10;
b.push(11);
```
Content: `[11, v: 10]`  
Length: `1` (Only numeric elements are counted in `length`).

---

**56. Different ways to create objects in JavaScript.**
1. **Object literal**: `let obj = {}`
2. **Constructor function**:
   ```javascript
   function Student(name) {
       this.name = name;
   }
   let obj = new Student("John");
   ```
3. **Object.create()**: `const obj = Object.create(proto);`
4. **Class syntax**:
   ```javascript
   class Student {
       constructor(name) {
           this.name = name;
       }
   }
   let obj = new Student("John");
   ```
5. **Object constructor**: `let obj = new Object();`

---

**57. How to implement inheritance in JavaScript?**
- **Prototypal inheritance**:
  ```javascript
  function Parent(name) {
      this.name = name;
  }
  Parent.prototype.greet = function () {
      console.log("Hello, " + this.name);
  };
  function Child(name) {
      Parent.call(this, name);
  }
  Child.prototype = Object.create(Parent.prototype);
  ```
- **Class-based inheritance**:
  ```javascript
  class Parent {
      constructor(name) {
          this.name = name;
      }
      greet() {
          console.log("Hello, " + this.name);
      }
  }
  class Child extends Parent {}
  ```

---

**58. Explain `call()`, `apply()`, and `bind()` methods.**
- **`call()`**: Calls a function with a specified `this` value and arguments.
- **`apply()`**: Similar to `call()`, but arguments are passed as an array.
- **`bind()`**: Returns a new function with a specified `this` value and arguments, which can be invoked later.

---

**59. What is event delegation in JavaScript?**
Event delegation allows you to attach a single event listener to a parent element to handle events for its child elements. It uses event bubbling.

Example:
```javascript
document.getElementById('parent').addEventListener('click', function (e) {
    if (e.target && e.target.nodeName === 'BUTTON') {
        console.log('Button clicked');
    }
});
```

---

**60. Key features of JavaScript.**
1. Single-threaded and event-driven.
2. Dynamically typed.
3. Prototypal inheritance.
4. First-class and higher-order functions.
5. Asynchronous handling with promises and async/await.


Here are the updated and simplified notes in a question-answer format:  

---

**61. What is the use of the “use strict” directive in JavaScript?**  
The "use strict" directive is used to enforce stricter parsing and error handling in JavaScript. It helps catch common mistakes like using undeclared variables and prevents the use of certain unsafe features.  

---

**62. What is event propagation in JavaScript?**  
Event propagation refers to how events travel through the DOM when triggered. It happens in two phases:  
- **Event Bubbling**: Events move from the innermost element to the outermost.  
- **Event Capturing**: Events move from the outermost element to the innermost.  

---

**63. What is event bubbling in JavaScript?**  
Event bubbling is the default event propagation method in which the event starts from the target element and travels upward through its ancestors in the DOM tree.  

---

**64. What is event capturing?**  
Event capturing is the opposite of event bubbling. The event starts from the outermost ancestor and travels inward to the target element. It can be enabled by passing `true` as the third parameter to the `addEventListener()` method.  

---

**65. What are callback functions in JavaScript?**  
A callback function is a function passed as an argument to another function, which gets called later when needed. For example:  
```javascript
button.addEventListener('click', function() {
    alert('Button clicked!');
});
```

---

**66. What is callback hell, and how can it be avoided?**  
Callback hell occurs when multiple nested callbacks are used, making the code difficult to read and debug. To avoid it, use **Promises** or **async/await** for managing asynchronous code.  

---

**67. What are Promises in JavaScript?**  
A Promise is an object representing the eventual completion or failure of an asynchronous operation.  
- **Pending**: Initial state.  
- **Fulfilled**: The operation completed successfully.  
- **Rejected**: The operation failed.  

---

**68. What is the use of async/await in JavaScript?**  
The `async` keyword declares an asynchronous function, while `await` pauses the function execution until a promise resolves, simplifying asynchronous code.  

---

**69. What is currying in JavaScript?**  
Currying is transforming a function with multiple arguments into a sequence of functions, each taking a single argument. Example:  
```javascript
function multiply(a) {
    return function(b) {
        return a * b;
    };
}
console.log(multiply(3)(2)); // Output: 6
```

---

**70. What is the purpose of the `defer` and `async` attributes in a `<script>` tag?**  
- **defer**: Loads the script in parallel but executes it after the HTML is fully parsed.  
- **async**: Loads and executes the script as soon as it is available, without waiting for the HTML to finish parsing.  

---

**71. What is a try-catch block in JavaScript?**  
A try-catch block is used for error handling. Code that may throw errors is placed in the `try` block. If an error occurs, the `catch` block handles it.  
```javascript
try {
    let result = riskyFunction();
} catch (error) {
    console.error("An error occurred:", error);
}
```

---

**72. How do you stop event propagation in JavaScript?**  
Use the `stopPropagation()` method to prevent an event from propagating further. Example:  
```javascript
element.addEventListener('click', function(event) {
    event.stopPropagation();
});
```

---

**73. How do you prevent the default behavior of an event in JavaScript?**  
Use the `preventDefault()` method to stop the default action associated with an event.  
```javascript
form.addEventListener('submit', function(event) {
    event.preventDefault();
    console.log('Form submission prevented!');
});
```

---

**74. What is CORS in JavaScript?**  
CORS (Cross-Origin Resource Sharing) is a security feature in browsers that controls how resources on a web page can be requested from a different domain. It ensures secure interaction between different origins.  

---

**75. What is debouncing in JavaScript?**  
Debouncing is a technique to limit the number of times a function is called. It ensures that the function executes only after a certain period of inactivity.  
Example:  
```javascript
function debounce(func, delay) {
    let timer;
    return function(...args) {
        clearTimeout(timer);
        timer = setTimeout(() => func.apply(this, args), delay);
    };
}
```

--- 
