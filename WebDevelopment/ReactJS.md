### **ReactJS Interview Questions with Answers**

---

#### **Basics**

---

**1. What is ReactJS, and why is it used?**  
- **Answer:**
  - ReactJS is a JavaScript library for building user interfaces, maintained by Facebook.
  - It is used for creating fast, interactive, and reusable UI components.

---

**2. What are the main features of ReactJS?**  
- **Answer:**
  - **JSX:** A syntax extension for writing HTML in JavaScript.
  - **Components:** Building blocks of a React application.
  - **Virtual DOM:** Improves performance by updating only the necessary parts of the DOM.
  - **Unidirectional Data Flow:** Data flows in one direction for better control.
  - **Declarative UI:** Makes code easier to understand and debug.

---

**3. What is JSX, and why is it used in React?**  
- **Answer:**
  - JSX stands for JavaScript XML. It allows writing HTML structures within JavaScript.
  - Example:
    ```javascript
    const element = <h1>Hello, World!</h1>;
    ```

---

**4. What are React components? How do functional and class components differ?**  
- **Answer:**
  - Components are reusable pieces of UI.
  - **Functional components:** Written as functions; use hooks for state and lifecycle.
  - **Class components:** Written as ES6 classes; use `state` and lifecycle methods.

---

**5. What is the difference between state and props in React?**  
- **Answer:**
  - **State:** A local data store for a component, mutable.
  - **Props:** Data passed from parent to child components, immutable.

---

**6. What is a React fragment, and why is it used?**  
- **Answer:**
  - A React fragment (`<React.Fragment>` or `<>`) allows grouping multiple elements without adding extra nodes to the DOM.

---

**7. What is the purpose of the `key` attribute in React lists?**  
- **Answer:**
  - The `key` attribute helps React identify and track individual list items efficiently when re-rendering.

---

**8. How does React manage the Virtual DOM?**  
- **Answer:**
  - React creates a virtual representation of the DOM, compares it with the real DOM, and updates only the changed elements.

---

**9. What is the difference between controlled and uncontrolled components?**  
- **Answer:**
  - **Controlled components:** Have state managed by React.
  - **Uncontrolled components:** Store state internally using DOM elements.

---

**10. What is React Router, and why is it used?**  
- **Answer:**
  - React Router is a library for routing in React applications, enabling navigation without reloading the page.

---

#### **Intermediate**

---

**1. What are React hooks? Explain `useState` and `useEffect` with examples.**  
- **Answer:**
  - Hooks are functions that let you use state and lifecycle features in functional components.
  - **`useState`:** Manages state in a functional component.
    ```javascript
    const [count, setCount] = useState(0);
    ```
  - **`useEffect`:** Runs side effects like fetching data or subscriptions.
    ```javascript
    useEffect(() => {
      document.title = `Count: ${count}`;
    }, [count]);
    ```

---

**2. What is the Context API, and how is it used in React?**  
- **Answer:**
  - Context API provides a way to share data globally without passing props through every component.
  - Example:
    ```javascript
    const ThemeContext = React.createContext();
    const App = () => (
      <ThemeContext.Provider value="dark">
        <Child />
      </ThemeContext.Provider>
    );
    ```

---

**3. How does React handle events differently from HTML?**  
- **Answer:**
  - React uses camelCase syntax for event handlers (e.g., `onClick`).
  - Event handling is done with synthetic events, ensuring cross-browser compatibility.

---

**4. What is the difference between `useMemo` and `useCallback`?**  
- **Answer:**
  - **`useMemo`:** Memorizes the return value of a function.
  - **`useCallback`:** Memorizes the function itself to prevent unnecessary re-renders.
  - Example:
    ```javascript
    const memoizedValue = useMemo(() => computeExpensiveValue(a, b), [a, b]);
    const memoizedCallback = useCallback(() => handleClick(a), [a]);
    ```

---

**5. How does lifting state up work in React?**  
- **Answer:**
  - Lifting state involves moving shared state to the nearest common ancestor for synchronization between components.

---

**6. What is the purpose of React Portals?**  
- **Answer:**
  - Portals render components outside the DOM hierarchy of their parent component.
  - Example:
    ```javascript
    ReactDOM.createPortal(<Child />, document.getElementById("portal-root"));
    ```

---

**7. How does error handling work in React using `ErrorBoundary`?**  
- **Answer:**
  - `ErrorBoundary` components catch JavaScript errors in child components.
  - Example:
    ```javascript
    class ErrorBoundary extends React.Component {
      state = { hasError: false };
      static getDerivedStateFromError() {
        return { hasError: true };
      }
      componentDidCatch(error, info) {
        console.error(error, info);
      }
      render() {
        return this.state.hasError ? <h1>Error occurred</h1> : this.props.children;
      }
    }
    ```

---

**8. What is Redux, and how does it work with React?**  
- **Answer:**
  - Redux is a state management library that centralizes application state.
  - React integrates Redux using the `react-redux` library.
  - Key components:
    - **Store:** Holds the state.
    - **Actions:** Describe what to do.
    - **Reducers:** Specify how state changes.

---

**9. What are higher-order components (HOCs) in React?**  
- **Answer:**
  - HOCs are functions that take a component and return a new component, enhancing functionality.
  - Example:
    ```javascript
    const withTheme = (Component) => (props) => (
      <div className="theme">
        <Component {...props} />
      </div>
    );
    ```

---

**10. How can you optimize the performance of a React application?**  
- **Answer:**
  - Use `React.memo` to avoid re-rendering.
  - Use `useMemo` and `useCallback`.
  - Split code using `React.lazy` and `Suspense`.
  - Avoid inline functions and heavy computations in render.
  - Implement pagination or infinite scroll for large datasets.

---
