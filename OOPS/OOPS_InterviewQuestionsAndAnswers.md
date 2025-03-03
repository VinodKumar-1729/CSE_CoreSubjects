# **Object-Oriented Programming (OOPs)**

## **What is OOPs?**  
- OOPs stands for **Object-Oriented Programming**.  
- It is a **programming paradigm** based on the concept of "objects."  
- Objects are instances of **classes** that encapsulate data and behavior.  
- The four **core principles** of OOPs:  
  1. **Encapsulation**  
  2. **Abstraction**  
  3. **Polymorphism**  
  4. **Inheritance**  

---

## **Why do we need OOPs?**  
- Provides **modularity** and organizes code better.  
- Ensures **data hiding** and security.  
- **Code reusability** through inheritance.  
- **Flexibility** using polymorphism.  
- Makes complex programs **more manageable**.  

---

## **Major Object-Oriented Programming Languages**  
- Java  
- C++  
- C#  
- Python  
- Ruby  
- Swift  
- Kotlin  

---

## **Key Features of OOPs**  

### **1. Encapsulation**  
- **Definition**: Bundling of data and methods that operate on that data into a **single unit** (class).  
- **Purpose**: To **restrict** direct access to some details of an object.  
- **Example**: Using **private** variables in a class and accessing them via **getter and setter** methods.  

#### **Example in Java**  
```java
class Student {
    private String name;

    // Setter method
    public void setName(String newName) {
        name = newName;
    }

    // Getter method
    public String getName() {
        return name;
    }
}
```

---

### **2. Inheritance**  
- **Definition**: One class (child/subclass) inherits properties and behaviors from another class (parent/superclass).  
- **Purpose**: To promote **code reuse** and maintain a hierarchical relationship between classes.  
- **Example in Java**:  
```java
class Animal {
    void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Dog barks");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dogObj = new Dog();
        dogObj.sound(); // Inherited from Animal class
        dogObj.bark();  // Dog-specific method
    }
}
```

#### **Types of Inheritance**  
1. **Single Inheritance** - One class inherits from another.  
2. **Multilevel Inheritance** - A derived class acts as a base class for another.  
3. **Multiple Inheritance** - A class inherits from more than one base class (supported in C++ but not in Java).  
4. **Hierarchical Inheritance** - Multiple classes inherit from a single base class.  
5. **Hybrid Inheritance** - A mix of multiple and hierarchical inheritance.  

---

### **3. Polymorphism**  
- **Definition**: One entity takes **multiple forms**.  
- **Purpose**: Increases **flexibility** in the program.  
- **Types**:  
  1. **Compile-time (Static) Polymorphism** → Achieved through method **overloading**.  
  2. **Runtime (Dynamic) Polymorphism** → Achieved through method **overriding**.  

#### **Method Overloading (Compile-time Polymorphism)**
```java
class MathOperations {
    int add(int a, int b) {
        return a + b;
    }

    double add(double a, double b) {
        return a + b;
    }
}

public class Main {
    public static void main(String[] args) {
        MathOperations obj = new MathOperations();
        System.out.println(obj.add(5, 10));      // Calls int version
        System.out.println(obj.add(5.5, 2.3));  // Calls double version
    }
}
```

#### **Method Overriding (Runtime Polymorphism)**
```java
class Parent {
    void display() {
        System.out.println("Display method in Parent class");
    }
}

class Child extends Parent {
    void display() {  // Overriding parent method
        System.out.println("Display method in Child class");
    }
}

public class Main {
    public static void main(String[] args) {
        Parent obj = new Child();  // Parent reference, child object
        obj.display();  // Calls Child class method (Runtime binding)
    }
}
```

---

### **4. Abstraction**  
- **Definition**: Hides **implementation details** and exposes only the essential features.  
- **Achieved via**:  
  1. **Abstract classes** (partially implemented classes).  
  2. **Interfaces** (fully abstract classes).  

#### **Abstract Class Example**
```java
abstract class Vehicle {
    abstract void start(); // Abstract method (no body)
}

class Car extends Vehicle {
    void start() {
        System.out.println("Car starts with key");
    }
}

public class Main {
    public static void main(String[] args) {
        Vehicle obj = new Car();
        obj.start();
    }
}
```

#### **Interface Example**
```java
interface Animal {
    void sound(); // Abstract method
}

class Dog implements Animal {
    public void sound() {
        System.out.println("Dog barks");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal obj = new Dog();
        obj.sound();
    }
}
```

---

## **Important Concepts in OOPs**

### **What is a Class?**
- A **class** is a blueprint/template for creating objects.  
- It contains **data members (variables)** and **methods (functions)**.  

### **What is an Object?**
- An object is an **instance** of a class.  
- It represents a **real-world entity** with **attributes and behavior**.  

### **What is a Constructor?**
- A **special method** called automatically when an object is created.  
- Used to **initialize object properties**.  

#### **Types of Constructors**  
1. **Default Constructor** - No parameters, provided by compiler if not defined.  
2. **Parameterized Constructor** - Accepts arguments for custom initialization.  
3. **Copy Constructor** - Copies data from another object of the same class.  

```java
class Person {
    String name;

    // Constructor
    Person(String n) {
        name = n;
    }

    // Copy Constructor
    Person(Person obj) {
        this.name = obj.name;
    }

    void display() {
        System.out.println("Name: " + name);
    }

    public static void main(String[] args) {
        Person p1 = new Person("Vinod");
        Person p2 = new Person(p1); // Copy constructor call
        p2.display();
    }
}
```

---

## **More Advanced OOPs Questions**

### **What is an Access Specifier?**
- Defines the **scope** and **visibility** of class members.  
- **Types**:  
  1. **Public** - Accessible anywhere.  
  2. **Private** - Accessible only within the same class.  
  3. **Protected** - Accessible within the same package and subclasses.  

---

### **super vs this keyword in Java**  
| Feature | `super` | `this` |
|---------|--------|--------|
| Refers to | Parent class | Current class |
| Used for | Accessing parent class members | Accessing current class members |
| Calls Constructor? | Yes, to call the parent class constructor (`super()`) | Yes, to call another constructor in the same class (`this()`) |
| Overriding | Used to call parent class methods when overridden in the child class | Used to differentiate instance variables from parameters |

Example:  
```java
class Parent {
    int a = 10;

    void display() {
        System.out.println("Parent class method");
    }
}

class Child extends Parent {
    int a = 20;

    void show() {
        System.out.println("Child class variable a: " + this.a); // Refers to current class variable
        System.out.println("Parent class variable a: " + super.a); // Refers to parent class variable
    }
}

public class Test {
    public static void main(String[] args) {
        Child obj = new Child();
        obj.show();
    }
}
```

---

### **static keyword in Java**  
- **Static Variable**: Shared among all objects, stored in the class area.  
- **Static Method**: Can be called without an object, cannot access non-static members directly.  
- **Static Block**: Runs once when the class is loaded.  
- **Static Class (Nested Class)**: A class inside another class that doesn’t need an outer class instance.

Example:  
```java
class Example {
    static int count = 0; // Static variable

    static void show() {  // Static method
        System.out.println("Static method called");
    }

    static {  // Static block
        System.out.println("Static block executed");
    }
}

public class Test {
    public static void main(String[] args) {
        Example.show(); // Calling static method without object
        System.out.println("Static variable: " + Example.count);
    }
}
```

---

### **Garbage Collection in Java**  
Garbage Collection (GC) automatically reclaims memory occupied by unused objects.  

- **Methods for requesting GC:**  
  - `System.gc();`
  - `Runtime.getRuntime().gc();`

- **Types of GC Algorithms:**  
  - **Serial GC**: Best for small applications.  
  - **Parallel GC**: Uses multiple threads for GC.  
  - **CMS (Concurrent Mark-Sweep) GC**: Low pause times, used in web servers.  
  - **G1 (Garbage First) GC**: Best for large applications.  

Example:  
```java
class Demo {
    protected void finalize() {
        System.out.println("Object is garbage collected");
    }
}

public class Test {
    public static void main(String[] args) {
        Demo d1 = new Demo();
        d1 = null;
        System.gc(); // Requesting GC
    }
}
```

---

### **Coupling in OOP**  
Coupling refers to the dependency between classes.  

- **Types:**  
  - **Tight Coupling**: High dependency between classes, difficult to modify.  
  - **Loose Coupling**: Minimal dependency, easier to modify.  

Example of **tight coupling** (bad practice):  
```java
class Engine {
    void start() {
        System.out.println("Engine started");
    }
}

class Car {
    Engine engine = new Engine(); // Car is tightly coupled with Engine

    void drive() {
        engine.start();
        System.out.println("Car is moving");
    }
}
```
Example of **loose coupling** (good practice using dependency injection):  
```java
class Engine {
    void start() {
        System.out.println("Engine started");
    }
}

class Car {
    private Engine engine;

    Car(Engine engine) {  // Injecting dependency
        this.engine = engine;
    }

    void drive() {
        engine.start();
        System.out.println("Car is moving");
    }
}

public class Test {
    public static void main(String[] args) {
        Engine engine = new Engine();
        Car car = new Car(engine); // Passing engine object
        car.drive();
    }
}
```

---

### **Friend Function in C++ (Not in Java)**  
- **A friend function** allows non-member functions to access private and protected members of a class.  
- **Not available in Java** (Java follows strict encapsulation).  

Example in **C++**:  
```cpp
#include <iostream>
using namespace std;

class Box {
private:
    int width;

public:
    Box(int w) : width(w) {}

    friend void showWidth(Box b); // Friend function declaration
};

void showWidth(Box b) { // Friend function definition
    cout << "Width: " << b.width << endl;
}

int main() {
    Box obj(10);
    showWidth(obj); // Accessing private data
}
```

---

### **Exception Handling in Java**  
- **Exception:** An unexpected event that disrupts program execution.  
- **Checked Exceptions:** Compile-time exceptions (e.g., IOException).  
- **Unchecked Exceptions:** Runtime exceptions (e.g., NullPointerException).  

**Try-Catch Example:**  
```java
public class Test {
    public static void main(String[] args) {
        try {
            int a = 10 / 0; // ArithmeticException
        } catch (ArithmeticException e) {
            System.out.println("Cannot divide by zero");
        } finally {
            System.out.println("Finally block executed");
        }
    }
}
```

**Throw vs Throws:**  
- **throw**: Used to manually throw an exception.  
- **throws**: Declares exceptions in a method signature.  

Example:  
```java
class Example {
    void check(int age) throws Exception {
        if (age < 18) throw new Exception("Not eligible");
    }
}

public class Test {
    public static void main(String[] args) {
        Example obj = new Example();
        try {
            obj.check(16);
        } catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }
}
```

---

### **Final vs Finally vs Finalize in Java**  
| Feature | `final` | `finally` | `finalize()` |
|---------|--------|-----------|-------------|
| Used for | Prevent inheritance, overriding, or modification | Ensures execution of cleanup code | Called before garbage collection |
| Applied to | Variables, methods, and classes | A block in exception handling | Objects |
| Execution | Compile-time | Runtime | GC time |
| Example | `final int x = 10;` | `finally { System.out.println("Always executed"); }` | `protected void finalize() { System.out.println("Garbage collected"); }` |

---

### **Abstraction vs Encapsulation**  
| Feature | Abstraction | Encapsulation |
|---------|------------|--------------|
| Definition | Hides implementation details and shows only functionality | Wrapping data and methods into a single unit |
| Achieved by | Abstract classes & Interfaces | Private variables with getter/setter methods |
| Example | `abstract class Shape { abstract void draw(); }` | `private int age; public int getAge() { return age; }` |

---

### What is method hiding?
**Method hiding** occurs when a subclass defines a static method with the same signature as a static method in the superclass. In such cases, the method in the subclass does not override the method in the superclass but instead hides it.

Example in Java:
```java
class Parent {
    static void show() {
        System.out.println("Parent's static method");
    }
}

class Child extends Parent {
    static void show() {
        System.out.println("Child's static method");
    }
}

public class Test {
    public static void main(String[] args) {
        Parent obj = new Child();
        obj.show(); // Outputs: Parent's static method (method hiding)
    }
}
```

---

### What is the difference between method overloading and method overriding?
| Feature | Method Overloading | Method Overriding |
|---------|--------------------|--------------------|
| Definition | Multiple methods with the same name but different parameters in the same class | Subclass provides a specific implementation of a method already defined in the superclass |
| Polymorphism Type | Compile-time (static) polymorphism | Runtime (dynamic) polymorphism |
| Signature Change | Yes, method signatures must be different | No, method signatures must be the same |
| Access Specifier | Can be the same or different | Cannot reduce visibility of overridden method |
| Static Methods | Can be overloaded | Cannot be overridden |

---

### What is early binding and late binding?
- **Early Binding (Static Binding)**: The method to be called is determined at compile-time. It applies to method overloading and static methods.
- **Late Binding (Dynamic Binding)**: The method to be called is determined at runtime, based on the object's actual type. It applies to method overriding.

Example:
```java
class Parent {
    void show() {
        System.out.println("Parent class");
    }
}

class Child extends Parent {
    void show() {
        System.out.println("Child class");
    }
}

public class Test {
    public static void main(String[] args) {
        Parent obj = new Child();
        obj.show(); // Late binding - calls Child's show()
    }
}
```

---

### What is an anonymous class?
An **anonymous class** is a class without a name, created for a short duration, often used when you need to override a method without explicitly defining a new subclass.

Example in Java:
```java
abstract class Animal {
    abstract void sound();
}

public class Main {
    public static void main(String[] args) {
        Animal obj = new Animal() {
            void sound() {
                System.out.println("Anonymous class sound!");
            }
        };
        obj.sound();
    }
}
```

---

### What is an inner class?
An **inner class** is a class defined within another class. It helps encapsulate functionality and improves modularity.

Types of inner classes:
1. **Member Inner Class** - Non-static class inside another class.
2. **Static Nested Class** - A static class inside another class.
3. **Local Inner Class** - Defined inside a method.
4. **Anonymous Inner Class** - A class without a name, declared and instantiated in one step.

Example:
```java
class Outer {
    class Inner {
        void display() {
            System.out.println("Inside Inner class");
        }
    }
}

public class Test {
    public static void main(String[] args) {
        Outer.Inner obj = new Outer().new Inner();
        obj.display();
    }
}
```

---

### What is object cloning?
**Object cloning** is the process of creating an exact copy of an object. In Java, this is done using the `clone()` method of the `Object` class.

Example:
```java
class Student implements Cloneable {
    String name;
    int age;

    Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    protected Object clone() throws CloneNotSupportedException {
        return super.clone();
    }
}

public class Test {
    public static void main(String[] args) throws CloneNotSupportedException {
        Student s1 = new Student("Vinod", 22);
        Student s2 = (Student) s1.clone();

        System.out.println(s2.name + " " + s2.age);
    }
}
```

---

### What is the difference between deep copy and shallow copy?
| Feature | Shallow Copy | Deep Copy |
|---------|-------------|-----------|
| Definition | Copies object reference, changes affect both objects | Creates a new independent copy |
| Memory Allocation | Same memory references | Allocates new memory for copied object |
| Cloning Mechanism | Default `clone()` method (Object class) | Custom cloning logic required |

---

### What is a singleton class?
A **singleton class** is a class that allows only one instance to exist at a time.

Example:
```java
class Singleton {
    private static Singleton instance;

    private Singleton() {} // Private constructor

    public static Singleton getInstance() {
        if (instance == null) {
            instance = new Singleton();
        }
        return instance;
    }
}

public class Test {
    public static void main(String[] args) {
        Singleton obj1 = Singleton.getInstance();
        Singleton obj2 = Singleton.getInstance();
        System.out.println(obj1 == obj2); // Output: true
    }
}
```

---

### What is dependency injection?
**Dependency Injection (DI)** is a design pattern used to inject dependencies into a class instead of creating them inside the class, improving modularity and testability.

Example:
```java
class Service {
    void serve() {
        System.out.println("Service is running");
    }
}

class Client {
    private Service service;

    Client(Service service) {
        this.service = service;
    }

    void useService() {
        service.serve();
    }
}

public class Test {
    public static void main(String[] args) {
        Service service = new Service();
        Client client = new Client(service);
        client.useService();
    }
}
```

---

### What is an immutable class?
An **immutable class** is a class whose objects cannot be modified once created. It ensures data consistency and thread safety.

Example:
```java
final class Immutable {
    private final String value;

    Immutable(String value) {
        this.value = value;
    }

    public String getValue() {
        return value;
    }
}

public class Test {
    public static void main(String[] args) {
        Immutable obj = new Immutable("Hello");
        System.out.println(obj.getValue());
    }
}
```

---

