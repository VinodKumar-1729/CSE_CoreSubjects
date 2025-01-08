

**Basic OOPS questions:**

---

### **1. What is OOPS?**
Object-Oriented Programming System (OOPS) is a programming paradigm that organizes data and behavior into "objects." Objects are instances of classes and contain attributes (data) and methods (functions) that operate on the data. OOPS is designed to improve code modularity, reusability, and scalability.

---

### **2. What are the main principles of OOPS? Explain each.**
The four main principles of OOPS are:
1. **Encapsulation**: Bundling data (attributes) and methods (functions) within a class and restricting direct access to some components.
   - Example: Private variables in a class with getter and setter methods.
   
2. **Inheritance**: Enabling one class (child/subclass) to acquire properties and behaviors of another class (parent/superclass).
   - Example: A `Car` class inheriting from a `Vehicle` class.

3. **Polymorphism**: Allowing methods to have different behaviors based on their usage or input.
   - Example: Method Overloading and Method Overriding.
   
4. **Abstraction**: Hiding implementation details and showing only the essential features.
   - Example: An interface or abstract class in Java.

---

### **3. Define the terms: Class and Object.**
- **Class**: A blueprint or template for creating objects. It defines attributes (variables) and methods (functions) that the objects of the class will have.
  - Example: A `Car` class defines properties like `color`, `model`, and methods like `start()` and `stop()`.
- **Object**: An instance of a class that contains specific data and can perform actions defined by the class.
  - Example: `myCar = new Car();`

---

### **4. What is the difference between a Class and an Object?**
| **Aspect**       | **Class**                                       | **Object**                              |
|-------------------|------------------------------------------------|-----------------------------------------|
| **Definition**    | A blueprint or template for objects.           | An instance of a class.                 |
| **Memory**        | Does not occupy memory until an object is created. | Occupies memory when instantiated.     |
| **Usage**         | Defines attributes and methods.                | Uses the attributes and methods of its class. |

---

### **5. What are the key features of OOPS?**
1. **Encapsulation**: Bundling data and methods together.
2. **Inheritance**: Reusing code through hierarchy.
3. **Polymorphism**: Implementing one interface in multiple forms.
4. **Abstraction**: Hiding complexities from users.
5. **Modularity**: Dividing the program into manageable units.
6. **Reusability**: Reusing existing code in new programs.

---

### **6. What is Encapsulation? Why is it important?**
Encapsulation is the process of wrapping data and methods into a single unit, typically a class, while restricting direct access to the data using access modifiers (e.g., `private`, `protected`). 
- **Importance**:
  1. **Data Security**: Prevents unauthorized access to data.
  2. **Code Maintainability**: Makes code easier to manage and update.
  3. **Abstraction**: Hides implementation details from the user.

---

### **7. What is Inheritance? Give examples.**
Inheritance is the mechanism by which a class (child/subclass) inherits properties and methods from another class (parent/superclass).
- **Example**:
  ```java
  class Animal {
      void eat() {
          System.out.println("This animal eats food.");
      }
  }
  class Dog extends Animal {
      void bark() {
          System.out.println("The dog barks.");
      }
  }
  Dog dog = new Dog();
  dog.eat(); // Output: This animal eats food.
  dog.bark(); // Output: The dog barks.
  ```

---

### **8. What is Polymorphism? Explain with examples.**
Polymorphism allows methods or functions to behave differently based on input or context.
1. **Compile-Time Polymorphism (Method Overloading)**:
   ```java
   class Math {
       int add(int a, int b) { return a + b; }
       double add(double a, double b) { return a + b; }
   }
   ```
2. **Run-Time Polymorphism (Method Overriding)**:
   ```java
   class Animal {
       void sound() { System.out.println("Animal makes a sound"); }
   }
   class Dog extends Animal {
       void sound() { System.out.println("Dog barks"); }
   }
   Animal animal = new Dog();
   animal.sound(); // Output: Dog barks
   ```

---

### **9. What is Abstraction? How is it implemented in OOPS?**
Abstraction is the process of hiding implementation details and showing only the necessary functionality.
- **Implementation**:
  - Using **Abstract Classes**:
    ```java
    abstract class Shape {
        abstract void draw();
    }
    class Circle extends Shape {
        void draw() { System.out.println("Drawing Circle"); }
    }
    ```
  - Using **Interfaces**:
    ```java
    interface Vehicle {
        void move();
    }
    class Car implements Vehicle {
        public void move() { System.out.println("Car is moving"); }
    }
    ```

---

### **10. What is a Constructor? What are its types?**
A constructor is a special method used to initialize objects of a class. It has the same name as the class and no return type.
- **Types**:
  1. **Default Constructor**: Provided by the compiler if no constructor is defined.
  2. **Parameterized Constructor**: Accepts arguments to initialize the object.
  3. **Copy Constructor**: Copies data from another object (not explicitly supported in Java).

---

### **11. Can you explain the difference between a Constructor and a Method?**
| **Aspect**          | **Constructor**                              | **Method**                              |
|----------------------|----------------------------------------------|-----------------------------------------|
| **Purpose**          | Initializes objects.                        | Executes code or performs actions.      |
| **Name**             | Same as the class name.                     | Can have any valid identifier.          |
| **Return Type**      | No return type (not even `void`).            | Has a return type.                      |
| **Call**             | Called automatically during object creation. | Explicitly called by the user.          |

---

### **12. What is a Destructor? How does it work?**
A destructor is a method used to free up resources when an object is destroyed. It is automatically invoked at the end of an object's lifecycle. 
- **In Java**: Handled by the Garbage Collector.
  ```java
  @Override
  protected void finalize() throws Throwable {
      System.out.println("Object is destroyed");
  }
  ```
- **In C++**: Defined explicitly using a `~` symbol.
  ```cpp
  ~ClassName() {
      // Code to free resources
  }
  ```

--- 

**Intermediate-level OOPS questions:**

---

### **1. What is the difference between Compile-Time and Run-Time Polymorphism?**

| **Aspect**                | **Compile-Time Polymorphism**                              | **Run-Time Polymorphism**                                |
|---------------------------|-----------------------------------------------------------|----------------------------------------------------------|
| **Definition**            | Polymorphism resolved at compile time.                    | Polymorphism resolved at runtime.                       |
| **Examples**              | Method Overloading, Operator Overloading.                 | Method Overriding.                                      |
| **Binding**               | Early Binding.                                            | Late Binding (Dynamic Binding).                        |
| **Execution**             | Faster as it is determined at compile time.               | Slower due to runtime method resolution.                |
| **Example** (Java)        | `add(int a, int b)` and `add(double a, double b)`.         | Overriding `void draw()` in subclasses like `Circle`.    |

---

### **2. Explain the difference between Method Overloading and Method Overriding.**

| **Aspect**                | **Method Overloading**                                    | **Method Overriding**                                    |
|---------------------------|----------------------------------------------------------|----------------------------------------------------------|
| **Definition**            | Same method name, different parameter list in the same class. | Same method name and parameters in parent and child classes. |
| **Polymorphism Type**     | Compile-Time Polymorphism.                                | Run-Time Polymorphism.                                   |
| **Inheritance Requirement** | Not required.                                           | Requires inheritance.                                    |
| **Modifiers**             | Can have different access modifiers.                     | Access modifiers must not reduce visibility.             |
| **Example** (Java)        | `void print(int x)` and `void print(double y)`.           | Parent class `void show()`, child class `void show()`.   |

---

### **3. Can we override static methods in Java? Why or why not?**
No, static methods cannot be overridden in Java because they are bound to the class rather than an object. Overriding applies to instance methods, which are tied to object instances. Instead, static methods can be **hidden**, meaning the method in the child class shadows the parent class's static method.

---

### **4. What is the difference between Abstraction and Encapsulation?**

| **Aspect**            | **Abstraction**                                           | **Encapsulation**                                       |
|-----------------------|----------------------------------------------------------|--------------------------------------------------------|
| **Definition**        | Hides implementation details and shows only functionality. | Restricts direct access to data through access modifiers. |
| **Focus**            | On what the object does (behavior).                       | On how the object is structured (data hiding).         |
| **Implementation**   | Abstract classes, Interfaces.                             | Classes, access modifiers.                             |
| **Example**           | Abstract class `Shape` with `draw()` method.             | Private fields with public getter/setter methods.      |

---

### **5. What are access modifiers? Explain their importance.**
Access modifiers define the visibility of classes, methods, and variables. In Java, they include:
1. **Private**: Accessible within the class only.
2. **Default (no modifier)**: Accessible within the same package.
3. **Protected**: Accessible within the package and by subclasses.
4. **Public**: Accessible everywhere.

**Importance**:
- Enforces encapsulation.
- Prevents unauthorized access to critical data.
- Defines scope and limits access.

---

### **6. What is Multiple Inheritance? Does Java support it? Why?**
**Multiple Inheritance**: When a class inherits from more than one class, gaining properties and behaviors from multiple parents.
- **Java's Support**: Java does not support multiple inheritance with classes to avoid the **Diamond Problem** (ambiguity due to multiple parent implementations of the same method).
- Java allows multiple inheritance using **interfaces**, as interfaces only provide method declarations, avoiding ambiguity.

---

### **7. Explain the concept of ‘super’ and ‘this’ keywords.**
- **`super`**:
  - Refers to the parent class.
  - Used to call a parent class’s constructor or method.
  - Example:
    ```java
    super.methodName();
    ```
- **`this`**:
  - Refers to the current class.
  - Used to access current class methods, variables, or constructors.
  - Example:
    ```java
    this.variableName = value;
    this.methodName();
    ```

---

### **8. How is the concept of OOPS implemented in popular programming languages like Java or Python?**
- **Java**:
  - Fully object-oriented (except for primitive types).
  - Uses classes and objects to implement all OOPS principles.
  - Features include inheritance, abstraction (via interfaces/abstract classes), encapsulation, and polymorphism.

- **Python**:
  - Multi-paradigm (supports both procedural and OOPS styles).
  - Implements OOPS through classes, inheritance, and polymorphism.
  - Dynamic typing makes it more flexible than Java.

---

### **9. What is the significance of the `final` keyword in OOPS?**
The `final` keyword is used to restrict modification:
1. **Final Variables**: Cannot be reassigned after initialization.
2. **Final Methods**: Cannot be overridden by subclasses.
3. **Final Classes**: Cannot be extended.
   - Example:
     ```java
     final class Constants {
         static final double PI = 3.14159;
     }
     ```

---

### **10. What is an Interface? How is it different from an Abstract Class?**

| **Aspect**            | **Interface**                                         | **Abstract Class**                                   |
|-----------------------|-------------------------------------------------------|----------------------------------------------------|
| **Definition**        | A collection of abstract methods (no implementation). | Can have both abstract and concrete methods.       |
| **Inheritance**       | Supports multiple inheritance.                        | Single inheritance only.                           |
| **Default Modifier**  | Methods are `public` and `abstract` by default.       | Methods can have any access modifier.             |
| **Example**           | `interface Drawable { void draw(); }`                 | `abstract class Shape { abstract void draw(); }`   |

---

### **11. What are Virtual Functions and Pure Virtual Functions?**
- **Virtual Functions**:
  - Methods declared in a base class that can be overridden in derived classes.
  - Supported in languages like C++.

- **Pure Virtual Functions**:
  - Virtual functions with no implementation in the base class.
  - Used to enforce implementation in derived classes (similar to abstract methods in Java).
  - Example:
    ```cpp
    class Shape {
        virtual void draw() = 0; // Pure virtual function
    };
    ```

---

### **12. Explain the concept of Dynamic Binding.**
Dynamic Binding (or Late Binding) refers to the process where the method to be invoked is determined at runtime. It is used in **method overriding** to call the appropriate version of the method based on the object type.
- Example:
  ```java
  Animal animal = new Dog();
  animal.sound(); // Calls Dog's overridden method
  ```

---

### **13. What is the Diamond Problem in inheritance? How is it resolved?**
The Diamond Problem occurs in multiple inheritance when a class inherits from two classes that have a common parent, leading to ambiguity in method resolution.
- **Resolution in Java**: Java avoids the Diamond Problem by not allowing multiple inheritance with classes. It supports multiple inheritance using interfaces, as interfaces do not contain implementation, only declarations.

--- 

**Advanced-level OOPS questions:**

---

### **1. Is it always necessary to create objects from a class in OOPS? Why or why not?**
No, creating objects from a class is not always necessary in OOPS. For example:
1. **Static Members**: Static methods and variables can be accessed without creating an object.
   ```java
   class Example {
       static void display() { System.out.println("Static method"); }
   }
   Example.display();
   ```
2. **Utility Classes**: Classes like `Math` in Java provide only static methods and are not instantiated.
3. **Abstract Classes and Interfaces**: These cannot be instantiated directly; instead, their concrete implementations are used.

---

### **2. Can a class implement multiple interfaces? Provide examples.**
Yes, a class can implement multiple interfaces in OOPS. This allows Java to achieve multiple inheritance.
```java
interface A { void methodA(); }
interface B { void methodB(); }

class C implements A, B {
    public void methodA() { System.out.println("Method A"); }
    public void methodB() { System.out.println("Method B"); }
}
```

---

### **3. How does the concept of Delegation fit into OOPS?**
**Delegation** is a design principle where an object delegates a task to another object. Instead of performing the task itself, it relies on another class or object to handle the responsibility.  
Example:
```java
class Printer {
    void print() { System.out.println("Printing..."); }
}

class Document {
    private Printer printer = new Printer();
    void printDocument() { printer.print(); } // Delegation
}
```

---

### **4. What are Design Patterns in OOPS? Can you name a few?**
**Design Patterns** are reusable solutions to common software design problems. Examples:
1. **Creational Patterns**: Singleton, Factory, Builder, Prototype.
2. **Structural Patterns**: Adapter, Decorator, Composite.
3. **Behavioral Patterns**: Observer, Strategy, State, Command.

---

### **5. Explain the difference between Association, Aggregation, and Composition.**

| **Aspect**      | **Association**                                   | **Aggregation**                               | **Composition**                                   |
|------------------|--------------------------------------------------|-----------------------------------------------|--------------------------------------------------|
| **Definition**   | A general relationship between objects.          | A "has-a" relationship where objects are loosely related. | A strong "has-a" relationship where objects are tightly bound. |
| **Lifetime**     | Independent.                                     | Independent.                                  | Dependent (child cannot exist without parent).   |
| **Example**      | Teacher ↔ Student.                               | Department ↔ Professor.                       | House ↔ Room (Room cannot exist without House). |

---

### **6. What is the role of Garbage Collection in OOPS?**
Garbage Collection automatically frees memory by destroying unused or unreachable objects. It ensures efficient memory management and prevents memory leaks.
- Example in Java: Objects with no references are eligible for garbage collection.

---

### **7. Can we create an object without a constructor? How?**
Yes, an object can be created without explicitly calling a constructor using:
1. **Cloning**: Using the `clone()` method in Java.
2. **Deserialization**: Reconstructing an object from a serialized form.
3. **Reflection**: Creating objects via the `Class.newInstance()` method.

---

### **8. What is a Singleton Class? Why is it used?**
A **Singleton Class** ensures only one instance of the class exists. It is used for scenarios like managing a shared resource (e.g., database connection, configuration settings).
Example:
```java
class Singleton {
    private static Singleton instance;
    private Singleton() {}
    public static Singleton getInstance() {
        if (instance == null) instance = new Singleton();
        return instance;
    }
}
```

---

### **9. Explain how you would achieve Thread Safety in an OOPS context.**
Thread safety ensures that shared resources are accessed correctly in multi-threaded environments. Methods:
1. **Synchronization**: Use `synchronized` blocks or methods.
2. **Locks**: Use `ReentrantLock` for finer control.
3. **Thread-Safe Collections**: Use `ConcurrentHashMap`, `CopyOnWriteArrayList`.
4. **Immutable Objects**: Design objects as immutable.

---

### **10. What are SOLID principles in OOPS? Explain each briefly.**
1. **S**ingle Responsibility Principle: A class should have only one reason to change.
2. **O**pen/Closed Principle: Classes should be open for extension but closed for modification.
3. **L**iskov Substitution Principle: Derived classes should be substitutable for their base classes.
4. **I**nterface Segregation Principle: Interfaces should be specific to avoid forcing classes to implement unused methods.
5. **D**ependency Inversion Principle: Depend on abstractions, not on concrete implementations.

---

### **11. What is Reflection in OOPS? How is it used?**
Reflection allows a program to inspect and manipulate its own structure and behavior at runtime.
- Example: Accessing private fields or methods.
```java
Class<?> cls = Class.forName("Example");
Method method = cls.getDeclaredMethod("privateMethod");
method.setAccessible(true);
method.invoke(obj);
```

---

### **12. What is Object Cloning? How is it achieved in Java?**
Object Cloning creates a duplicate of an object.  
- Achieved by implementing the `Cloneable` interface and overriding the `clone()` method.
```java
class Example implements Cloneable {
    public Object clone() throws CloneNotSupportedException {
        return super.clone();
    }
}
```

---

### **13. Can you explain the difference between Shallow Copy and Deep Copy?**

| **Aspect**        | **Shallow Copy**                                   | **Deep Copy**                                       |
|-------------------|----------------------------------------------------|----------------------------------------------------|
| **Definition**    | Copies the object and references of inner objects. | Copies the object and duplicates inner objects.    |
| **Effect**        | Changes to inner objects affect the copied object. | Changes to inner objects do not affect the copy.   |
| **Example**       | `clone()` method without custom implementation.    | Manually copying fields or using serialization.    |

---

### **14. What are Anonymous Inner Classes? Why are they used?**
Anonymous Inner Classes are unnamed classes used to create one-time-use subclasses or implementations of interfaces.
Example:
```java
Runnable r = new Runnable() {
    public void run() { System.out.println("Anonymous Inner Class"); }
};
```

**Use**: Reduces boilerplate code for small, single-use implementations.

---

### **15. What is Dependency Injection in OOPS? How does it enhance code reusability?**
**Dependency Injection** (DI) provides objects their dependencies rather than creating them internally.  
- Enhances code reusability by decoupling object creation from business logic.
- Example using a constructor:
```java
class Service {
    private Repository repository;
    Service(Repository repository) {
        this.repository = repository; // Dependency injected
    }
}
```

--- 
