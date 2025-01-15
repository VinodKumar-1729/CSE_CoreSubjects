### *Object-Oriented Programming (OOP) Concepts**

---

### **1. Abstraction**
- **Definition**: 
  Abstraction is the process of hiding the internal implementation details and exposing only the essential features of an object. It helps in reducing complexity and allows focusing on what an object does rather than how it does it.
  
- **Real-World Example**: 
  A car's user interface (steering wheel, pedals) hides the engine's internal mechanics.

- **In Programming**:
  - Achieved through abstract classes and interfaces.
  - **Example in Java**:
    ```java
    abstract class Animal {
        abstract void sound();
    }
    class Dog extends Animal {
        void sound() {
            System.out.println("Bark");
        }
    }
    ```

---

### **2. Association**
- **Definition**: 
  Association represents a relationship between two classes. It establishes how objects of one class are connected to objects of another class.
  
- **Types of Association**:
  - **One-to-One**: A student has one roll number.
  - **One-to-Many**: A teacher teaches multiple students.
  - **Many-to-Many**: Multiple students enroll in multiple courses.

- **Example**:
    ```java
    class Student {
        String name;
        Student(String name) { this.name = name; }
    }
    class Teacher {
        String name;
        Teacher(String name) { this.name = name; }
    }
    ```

---

### **3. Encapsulation**
- **Definition**: 
  Encapsulation is the bundling of data and methods that operate on the data into a single unit (class). It also involves restricting direct access to certain details of an object.
  
- **Key Benefits**:
  - Ensures data security.
  - Promotes modularity.
  - Hides the implementation from users.
  
- **Example in Java**:
    ```java
    class Employee {
        private String name;
        private int id;
        public void setName(String name) { this.name = name; }
        public String getName() { return name; }
    }
    ```

---

### **4. Composition**
- **Definition**: 
  Composition is a "has-a" relationship where an object contains another object, and the contained object's lifecycle depends on the containing object.
  
- **Example**: 
  A library contains books. If the library is deleted, so are the books.
  
- **Example in Code**:
    ```java
    class Book {
        String title;
        Book(String title) { this.title = title; }
    }
    class Library {
        Book book;
        Library(String title) { this.book = new Book(title); }
    }
    ```

---

### **5. Polymorphism**
- **Definition**: 
  Polymorphism allows objects to be treated as instances of their parent class rather than their actual class. It enables one interface to be used for a general class of actions.
  
- **Types**:
  - **Compile-time Polymorphism (Method Overloading)**:
    Methods with the same name but different parameters.
  - **Run-time Polymorphism (Method Overriding)**:
    Subclass provides a specific implementation of a method already defined in its parent class.

- **Example of Method Overloading**:
    ```java
    class Math {
        int add(int a, int b) { return a + b; }
        double add(double a, double b) { return a + b; }
    }
    ```

- **Example of Method Overriding**:
    ```java
    class Animal {
        void sound() { System.out.println("Animal sound"); }
    }
    class Cat extends Animal {
        void sound() { System.out.println("Meow"); }
    }
    ```

---

### **6. Aggregation**
- **Definition**: 
  Aggregation is a "has-a" relationship similar to composition, but the lifecycle of the contained object is independent of the containing object.
  
- **Example**: 
  A department contains employees, but employees can exist independently.

- **Example in Code**:
    ```java
    class Employee {
        String name;
        Employee(String name) { this.name = name; }
    }
    class Department {
        List<Employee> employees;
        Department(List<Employee> employees) { this.employees = employees; }
    }
    ```

---

### **7. Inheritance**
- **Definition**: 
  Inheritance allows a class (child) to inherit fields and methods from another class (parent). It promotes code reusability and establishes an "is-a" relationship.
  
- **Types**:
  - **Single Inheritance**: One child inherits from one parent.
  - **Multi-level Inheritance**: Child inherits from a parent, which inherits from another parent.
  - **Hierarchical Inheritance**: Multiple children inherit from the same parent.

- **Example**:
    ```java
    class Vehicle {
        void start() { System.out.println("Vehicle starts"); }
    }
    class Car extends Vehicle {
        void start() { System.out.println("Car starts"); }
    }
    ```

---

### **8. Message Passing**
- **Definition**: 
  Message passing refers to the communication between objects by invoking methods. This is a fundamental concept of object-oriented design.
  
- **Characteristics**:
  - Objects call methods on each other.
  - Promotes modular design.

- **Example in Java**:
    ```java
    class Sender {
        void sendMessage(String message) {
            System.out.println("Sending message: " + message);
        }
    }
    class Receiver {
        void receive(Sender sender, String message) {
            sender.sendMessage(message);
        }
    }
    ```

---
