### Java Notes

#### 1. **Is Java Platform Independent? If yes, how?**
Yes, Java is a platform-independent language. Unlike many programming languages, `javac` compiles the source code into bytecode or a `.class` file. This bytecode is independent of the underlying operating system or hardware and can be executed on any platform that has a JVM (Java Virtual Machine).

Although the JVM itself is platform-dependent (different for each operating system), the bytecode can be executed on any system with a compatible JVM, making Java platform-independent.

---

#### 2. **What are the top Java features?**
Java has several features that make it one of the most widely used programming languages:

1. **Simple**: Easy to learn with a clean syntax.
2. **Platform Independent**: Write once, run anywhere (WORA).
3. **Interpreted and Compiled**: Combines compilation with interpretation for better performance.
4. **Robust**: Features like garbage collection and exception handling enhance reliability.
5. **Object-Oriented**: Supports key OOP concepts like inheritance, polymorphism, encapsulation, and abstraction.
6. **Secure**: Bytecode execution through JVM ensures security by preventing unauthorized access.
7. **High Performance**: Faster execution through JIT compilation.
8. **Dynamic**: Supports dynamic loading of classes and libraries.
9. **Distributed**: Facilitates building distributed applications using RMI and EJB.
10. **Multithreaded**: Supports concurrent execution of multiple threads.
11. **Architecture Neutral**: Not tied to specific hardware architecture.

---

#### 3. **What is JVM?**
JVM (Java Virtual Machine) is a Java interpreter responsible for:
- Loading bytecode.
- Verifying its integrity.
- Executing the bytecode.

Although the JVM is platform-dependent (varies with operating systems), it abstracts the platform-specific details from the programmer, enabling Java’s platform independence.

---

#### 4. **What is JIT?**
JIT (Just-In-Time) Compiler is part of the JVM and optimizes Java application performance by:

1. Compiling bytecode into native machine code at runtime.
2. Activating only when a method is invoked, reducing overhead.
3. Allowing the JVM to directly execute the compiled code for faster performance.

---

#### 5. **What are the memory areas available in JVM?**
JVM memory is divided into:

1. **Class (Method) Area**: Stores runtime constant pools, field and method data, and bytecode.
2. **Heap**: Allocates memory for objects at runtime.
3. **Stack**: Stores method-specific values and partial results.
4. **Program Counter Register**: Holds the address of the current instruction being executed.
5. **Native Method Stack**: Contains information about native (non-Java) methods.

---

#### 6. **What is a ClassLoader?**
ClassLoader is part of the JRE responsible for dynamically loading Java classes and interfaces into the JVM at runtime. It ensures that the runtime system does not need prior knowledge of the file structure.

---

#### 7. **What are the differences between JVM, JRE, and JDK?**

| Component | Description |
|-----------|-------------|
| **JVM** | Converts bytecode to machine code. Platform-dependent but enables platform independence for Java. |
| **JRE** | Java Runtime Environment; includes JVM and libraries needed to run Java programs. |
| **JDK** | Java Development Kit; includes JRE and development tools for writing and compiling Java programs. |

---

#### 8. **What are the differences between Java and C++?**

| Aspect | C++ | Java |
|--------|-----|------|
| **Platform** | Platform-dependent | Platform-independent |
| **Application** | System programming | Application programming |
| **Hardware Interaction** | Closer to hardware | Abstracted from hardware |
| **Global Scope** | Supports global scope | No global scope |
| **Unsupported Features** | Threads, documentation comments, unsigned right shift (>>>) | Goto, pointers, call by reference, structures, unions |
| **Inheritance Tree** | Creates new inheritance tree | Single inheritance tree (all classes inherit from `Object`) |

---

#### 9. **Explain `public static void main(String[] args)` in Java.**
- **public**: Accessible globally; JVM calls it from outside the class.
- **static**: Allows calling the method without creating an instance of the class.
- **void**: Indicates that the method does not return a value.
- **main**: The entry point for Java programs.
- **String[] args**: Stores command-line arguments passed during program execution.

---

#### 10. **What is Java String Pool?**
The Java String Pool is a special area in the heap memory where string literals are stored. When a new string is created:

- JVM checks the pool for an existing string with the same value.
- If found, the reference to the existing string is returned.
- If not, a new string object is created in the pool.

Example:
```java
String str1 = "Hello"; // Stored in the pool
String str2 = "Hello"; // Points to the same object in the pool
```

---

#### 11. **What happens if we don't declare the main method as static?**
If the main method is not declared as `static`, the program will compile but fail to run because the JVM requires the main method to be static as it calls the method without creating an instance of the class.

---

#### 12. **What are Packages in Java?**
Packages are used to group related classes, interfaces, and sub-packages for better organization, access control, and namespace management.

---

#### 13. **Why are Packages used?**
Packages are used to:
- Prevent naming conflicts.
- Control access levels.
- Organize classes for easier maintenance and readability.
- Provide hidden classes accessible only within the package.

---

#### 14. **What are the advantages of Packages?**
- Avoid name clashes.
- Simplify access control.
- Facilitate hidden class implementations.
- Improve organization and reusability.

---

#### 15. **How many types of packages are there in Java?**
1. **User-defined packages**: Created by developers for custom organization.
2. **Built-in packages**: Provided by Java (e.g., `java.util`, `java.io`).

---

#### 16. **Explain data types in Java.**
- **Primitive Data Types**:
  1. boolean: true/false
  2. byte: 8-bit integer (-128 to 127)
  3. char: 16-bit Unicode character
  4. short: 16-bit integer
  5. int: 32-bit integer
  6. long: 64-bit integer
  7. float: 32-bit floating-point
  8. double: 64-bit floating-point

- **Non-Primitive Data Types**:
  - Strings
  - Arrays
  - Classes
  - Objects
  - Interfaces

---

#### 17. **When is the byte datatype used?**
The `byte` datatype is used when:
- Memory efficiency is crucial.
- The range of values is within −128 to 127.

---

#### 18. **Can we declare pointers in Java?**
No, Java does not support pointers to ensure security and abstraction from memory management.

---

#### 19. **What is the default value of the byte datatype in Java?**
The default value of the `byte` datatype is `0`.

---

#### 20. **What are the default values of float and double in Java?**
- **float**: 0.0f
- **double**: 0.0d

