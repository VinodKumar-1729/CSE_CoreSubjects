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

**21. What is the Wrapper class in Java?**
A Wrapper class in Java encapsulates a primitive data type into an object. Java has 8 built-in wrapper classes: Boolean, Byte, Short, Integer, Character, Long, Float, and Double. Custom wrapper classes can also be created.

**22. Why do we need wrapper classes?**
- Wrapper classes are final and immutable.
- They provide useful methods like `valueOf()`, `parseInt()`.
- They enable autoboxing and unboxing (automatic conversion between primitives and objects).

**23. Differentiate between instance and local variables.**
- **Instance Variable**: Declared outside methods, has a default value, accessible throughout the class.
- **Local Variable**: Declared inside methods, no default value, scope limited to the method.

**24. What are the default values assigned to variables in Java?**
- Numeric types: `0`
- Boolean: `false`
- Object types: `null`
- Char: `\u0000` (null character)

**25. What is a Class Variable?**
A class variable (or static variable) is declared using the `static` keyword. It is shared among all instances of the class and exists only once, regardless of how many objects are created.

**26. What is the default value stored in local variables?**
Local variables do not have default values and must be initialized before use.

**27. Difference between instance and class variables.**
- **Instance Variable**: Specific to an object, different values for each object.
- **Class Variable**: Shared by all objects, declared with `static` keyword.

**28. What is a static variable?**
A static variable is shared among all instances of a class. It is created once at the class level and retains its value across all objects.

**29. Difference between System.out, System.err, and System.in.**
- **System.out**: Standard output stream, used for displaying results.
- **System.err**: Standard error stream, used for displaying error messages (usually in red in IDEs).
- **System.in**: Standard input stream, used for reading user input (commonly via `Scanner`).

**30. What is an IO stream?**
An IO stream represents an input source or an output destination. It allows reading and writing of data like objects, files, and characters.

**31. Difference between Reader/Writer and InputStream/OutputStream classes.**
- **Reader/Writer**: Handles characters, supports Unicode.
- **InputStream/OutputStream**: Handles raw byte data, suitable for binary files.

**32. What are the superclasses of all streams?**
- Byte streams: `InputStream` and `OutputStream`
- Character streams: `Reader` and `Writer`

**33. What are FileInputStream and FileOutputStream?**
- **FileInputStream**: Reads data from a file as bytes.
- **FileOutputStream**: Writes data to a file as bytes.

**34. Purpose of BufferedInputStream and BufferedOutputStream.**
Buffered streams improve performance by reducing the number of read/write operations. Data is temporarily stored in a buffer before being read or written.

**35. What are FilterStreams?**
FilterStreams process data in some way before passing it along, e.g., compressing or encrypting data. Example:
```java
FileInputStream fis = new FileInputStream("file_path");
BufferedInputStream bis = new BufferedInputStream(fis);
```

**36. What is an I/O filter?**
An I/O filter reads from one stream and writes data to another, transforming the data in the process. It is commonly used for tasks like compression.

**37. Ways to take input from the console in Java.**
1. Command-line arguments
2. BufferedReader
3. Console class
4. Scanner class

**38. Difference between print, println, and printf.**
- **print**: Prints data without a newline.
- **println**: Prints data and moves the cursor to the next line.
- **printf**: Prints data with formatted output using format specifiers.

**39. What are operators in Java?**
Operators are symbols used to perform operations on variables and values (e.g., `+`, `-`, `*`).

**40. Types of operators in Java.**
1. Arithmetic Operators
2. Unary Operators
3. Assignment Operator
4. Relational Operators
5. Logical Operators
6. Ternary Operator
7. Bitwise Operators
8. Shift Operators
9. `instanceof` Operator

1. **What is the difference between >> and >>> operators?**
   - `>>` shifts bits while preserving the sign bit.
   - `>>>` shifts bits and fills zeroes regardless of the sign.

2. **Which Java operator is right associative?**
   - The assignment operator `=` is right associative.

3. **What is the dot operator in Java?**
   - It is used to access members (fields and methods) of a class or an object.

4. **What is covariant return type?**
   - It allows an overriding method to return a subtype of the parent class's return type.

5. **What is the transient keyword?**
   - It marks a variable to be excluded during serialization.

6. **What’s the difference between sleep() and wait()?**
   - `sleep()`: Pauses the thread for a specified time but doesn’t release the lock.
   - `wait()`: Pauses the thread until notified and releases the lock.

7. **What are the differences between String and StringBuffer?**
   - `String`: Immutable.
   - `StringBuffer`: Mutable and thread-safe.

8. **What are the differences between StringBuffer and StringBuilder?**
   - `StringBuffer`: Thread-safe but slower.
   - `StringBuilder`: Not thread-safe but faster.

9. **Which is preferred between StringBuffer and StringBuilder for frequent updates?**
   - Use `StringBuffer` for thread safety and `StringBuilder` for better performance in single-threaded environments.

10. **Why is StringBuffer called mutable?**
    - It allows modification of its content without creating a new object.

11. **How is the creation of a String using new() different from a literal?**
    - Literal: Stored in String pool.
    - `new()`: Stored in heap memory, creating a new instance every time.

12. **What is an array in Java?**
    - A collection of fixed-size elements of the same type accessed via indices.

13. **On which memory are arrays created in Java?**
    - Arrays are created in heap memory.

14. **What are the types of arrays?**
    - Single-dimensional and Multi-dimensional arrays.

15. **Why does the Java array index start with 0?**
    - The index represents an offset from the start of the array.

16. **What is the difference between int array[] and int[] array?**
    - No functional difference; `int[] array` is preferred for readability.

17. **How to copy an array in Java?**
    - Use methods like `clone()`, `System.arraycopy()`, `Arrays.copyOf()`, or `Arrays.copyOfRange()`.

18. **What is a jagged array?**
    - A 2D array where rows have different lengths.

19. **Is it possible to make an array volatile?**
    - No, but individual elements of the array can be declared volatile.

20. **What are the advantages and disadvantages of an array?**
    - **Advantages**: Fast access, memory efficiency.
    - **Disadvantages**: Fixed size, rigid structure, inefficient resizing.

21. **What is an object-oriented paradigm?**
    - A programming style using objects, inheritance, and encapsulation to design solutions.

22. **What are the main concepts of OOPs in Java?**
    - Inheritance, Polymorphism, Abstraction, and Encapsulation.

23. **What is the difference between object-oriented and object-based programming languages?**
    - Object-oriented supports inheritance, polymorphism, and abstraction.
    - Object-based focuses only on encapsulation and objects.

24. **How is the new operator different from newInstance()?**
    - `new`: Creates objects at compile-time.
    - `newInstance()`: Creates objects at runtime using reflection.

25. **What are Classes in Java?**
    - Blueprints for creating objects, containing fields and methods defining object behavior.

66. **What is the difference between static (class) method and instance method?**

| Static (Class) Method                              | Instance Method                                    |
|----------------------------------------------------|---------------------------------------------------|
| Associated with a class rather than an object.     | Associated with an object rather than a class.    |
| Can be called using the class name without creating an instance. | Called on a specific instance using an object reference. |
| Does not have access to `this` keyword.            | Has access to `this` keyword.                    |
| Can access only static members.                   | Can access both static and non-static members.    |
| Cannot be overridden (resolved at compile time).  | Can be overridden (resolved at runtime).         |

---

67. **What is the `this` keyword in Java?**
- `this` is a keyword used to refer to the current object of a class.

---

68. **What are Access Specifiers and their types?**
- Access Specifiers in Java restrict the scope of a class, method, or data member.
  - **Public**: Accessible everywhere.
  - **Private**: Accessible only within the class.
  - **Protected**: Accessible within the package and subclasses.
  - **Default**: Accessible only within the package.

---

69. **What is the initial value of an object reference defined as an instance variable?**
- The initial value is `null`.

---

70. **What is an object?**
- An object is an instance of a class that represents real-world entities and has properties (attributes) and methods (behaviors).

---

71. **What are the different ways to create objects in Java?**
1. Using `new` keyword.
2. Using `Class.newInstance()`.
3. Using `clone()` method.
4. Using deserialization.
5. Using `Constructor.newInstance()`.

---

72. **What are the advantages and disadvantages of object cloning?**

**Advantages:**
- Reduces code size.
- Faster for replicating complex objects.
- Simplifies the copying of objects.

**Disadvantages:**
- Requires the `Cloneable` interface.
- Performs shallow copying by default.
- Need to override `clone()` for deep copying.

---

73. **What are the advantages of passing `this` into a method?**
- `this` is immutable and cannot be reassigned.
- Ensures thread safety when used in synchronized blocks.

---

74. **What is a constructor?**
- A constructor is a special method used to initialize an object. It has the same name as the class and no return type.

**Example:**
```java
class XYZ {
    private int val;
    XYZ() {
        val = 0; // Constructor initializes value
    }
}
```

---

75. **What happens if you don’t provide a constructor in a class?**
- The compiler generates a default constructor with no arguments and no operations.

---

76. **How many types of constructors are there in Java?**
1. **Default Constructor**: Takes no parameters and assigns default values.
   ```java
   className() {}
   ```
2. **Parameterized Constructor**: Accepts arguments to initialize object attributes.
   ```java
   className(param1, param2) {}
   ```

---

77. **What is the purpose of a default constructor?**
- Initializes an object with default values when no arguments are provided.

---

78. **What is a copy constructor?**
- A constructor that creates a new object by copying another object’s properties.

---

79. **Where and how can you use a private constructor?**
- Used to prevent instantiation of a class from outside (e.g., in Singleton classes).

---

80. **What are the differences between constructors and methods?**

| Constructor                                   | Method                                        |
|-----------------------------------------------|----------------------------------------------|
| Used to initialize an object.                | Used to perform specific actions.            |
| Same name as the class.                      | Can have any name.                           |
| No return type.                              | Must have a return type (or `void`).         |
| Called once during object creation.          | Can be called multiple times.               |

---

81. **What is an interface?**
- A blueprint for a class that contains only static constants and abstract methods.

**Syntax:**
```java
interface InterfaceName {
    void method(); // Abstract method
}
```

---

82. **What are the features of an interface?**
- Provides full abstraction.
- Supports multiple inheritance.
- Ensures loose coupling.
- Can contain default and static methods (from Java 8 onwards).

---

83. **What is a marker interface?**
- An empty interface with no methods or fields. Examples: `Serializable`, `Cloneable`.

---

84. **What are the differences between abstract class and interface?**

| Abstract Class                              | Interface                                    |
|---------------------------------------------|---------------------------------------------|
| Can have abstract and concrete methods.     | Contains only abstract methods (till Java 7). |
| Can have private, protected, or public members. | Members are `public` by default.            |
| Supports single inheritance.                | Supports multiple inheritance.              |
| Declared using `abstract` keyword.          | Declared using `interface` keyword.         |

---

85. **What do you mean by data encapsulation?**
- Bundling data and methods into a single unit, and restricting access to data by making it private.

---

86. **What are the advantages of encapsulation in Java?**
1. Hides implementation details (data hiding).
2. Provides flexibility (e.g., read-only or write-only variables).
3. Improves reusability and testability.
4. Enhances maintainability.

---

87. **What is the primary benefit of encapsulation?**
- Protects the internal state of an object from unauthorized access and modification.

---

88. **What do you mean by aggregation?**
- A "has-a" relationship between classes where one class contains a reference to another.

---

89. **What is the ‘IS-A’ relationship in OOP?**
- A relationship where one class inherits another class.

---

90. **Define inheritance.**
- When a subclass inherits properties and behaviors of a superclass. It provides code reusability and represents an "is-a" relationship.

**Java Interview Notes: Inheritance and Related Concepts**

1. **What are the different types of inheritance in Java?**
   - **Single Inheritance**: A subclass inherits from a single superclass.
   - **Multilevel Inheritance**: A class inherits from another subclass, creating a chain.
   - **Hierarchical Inheritance**: Multiple subclasses inherit from the same superclass.
   - **Multiple Inheritance**: Supported only with interfaces in Java, not with classes.

2. **What is multiple inheritance? Is it supported by Java?**
   - Multiple inheritance allows a class to inherit from multiple parent classes.
   - Java supports multiple inheritance only through interfaces, not classes, to avoid conflicts like the "diamond problem."

3. **How is inheritance in C++ different from Java?**
   - C++ supports multiple inheritance for classes; Java does not.
   - In C++, classes exist independently. In Java, all classes implicitly inherit from the `Object` class.

4. **What are the limitations of using inheritance?**
   - Inheritance can make subclasses tightly coupled with superclasses.
   - Overuse may lead to a complex and error-prone hierarchy.

5. **Why is composition preferred over inheritance?**
   - **Tight Coupling**: Changes in the superclass affect all subclasses.
   - **Fragile Base Class Problem**: Modifying the base class can break subclasses.
   - **Limited Reuse**: Subclasses inherit unnecessary properties, leading to complexity.

6. **What is an association?**
   - Association represents a "has-a" relationship between two classes via their objects.

7. **What is aggregation?**
   - A weaker form of association where objects can exist independently (e.g., a classroom and students).

8. **What is composition in Java?**
   - A strong form of association where the child cannot exist independently of the parent (e.g., a human and their heart).

9. **Difference between composition and aggregation?**
   - **Aggregation**: Objects are independent (empty diamond).
   - **Composition**: Objects are dependent (filled diamond).

10. **Can constructors be inherited?**
    - No, constructors cannot be inherited in Java.

11. **What is polymorphism?**
    - Polymorphism allows an entity to take multiple forms. It is of two types:
      - **Compile-time polymorphism (Method Overloading)**.
      - **Run-time polymorphism (Method Overriding)**.

12. **What is runtime polymorphism (dynamic method dispatch)?**
    - It resolves method calls during runtime based on the object's type.
    - Achieved through method overriding.

13. **What is method overriding?**
    - A subclass provides its implementation for a method defined in the superclass.
    - The method must have the same name, parameters, and return type.

14. **What is method overloading?**
    - Multiple methods in the same class have the same name but different parameters.
    - Achieves compile-time polymorphism.

15. **Can we override static methods?**
    - No, static methods belong to the class, not objects, so they cannot be overridden.

16. **Can we overload the `main()` method?**
    - Yes, we can overload the `main()` method, but the JVM always calls the standard `main(String[] args)`.

17. **Can private methods be overridden?**
    - No, private methods are not accessible outside the class, so they cannot be overridden.

18. **Can we change the scope of an overridden method?**
    - Yes, but the scope must be equal to or broader than the superclass method.

19. **Can we modify the `throws` clause in an overridden method?**
    - Yes, but the subclass can only declare the same exception, a subclass exception, or no exception.

20. **Does Java support virtual functions?**
    - Yes, all non-static methods in Java are virtual by default.

21. **What is abstraction?**
    - Abstraction hides implementation details and shows only essential features.

22. **What is an abstract class?**
    - A class that cannot be instantiated and may contain abstract (unimplemented) methods.

23. **When are abstract methods used?**
    - When a parent class wants its child classes to provide specific implementations for methods.

115. **What is the difference between method overloading and method overriding?**
    - **Method Overloading**:
      - Same class, different parameters.
      - Compile-time polymorphism.
      - Does not require inheritance.
    - **Method Overriding**:
      - Different classes, same method signature.
      - Runtime polymorphism.
      - Requires inheritance.

