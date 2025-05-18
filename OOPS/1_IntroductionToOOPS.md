

## ✅ **Object-Oriented Programming (OOP)**

---

### 🟩 **Definition**

**Object-Oriented Programming (OOP)** is a programming paradigm based on the concept of "objects", which can contain data in the form of **fields** (attributes or properties) and code in the form of **methods** (functions or procedures).

---

### 🟦 **Concept**

OOP models real-world entities as objects, which makes complex software easier to understand, maintain, and scale.
In OOP, programs are designed around data (objects) and the operations (methods) that work on that data.

Each object is an **instance** of a class — a blueprint for the object.
This paradigm promotes code **reusability**, **modularity**, and **flexibility**.

---

### 🟨 **Practical Use Case**

📱 **Example:** Suppose you're developing a **ride-sharing app like Uber**:

* You can have classes like `Driver`, `Passenger`, `Ride`, `Payment`.
* Each class has its own data and functions:

  * `Driver` class may have `name`, `car details`, and a method `acceptRide()`.
  * `Ride` class may calculate `distance`, `fare`, etc.

This separation makes the code modular and easy to update.

---

### 🟧 **Code Example in C++**

```cpp
#include <iostream>
using namespace std;

class Car {
private:
    string brand;
    int speed;

public:
    Car(string b, int s) {
        brand = b;
        speed = s;
    }

    void accelerate() {
        speed += 10;
        cout << brand << " accelerated to " << speed << " km/h" << endl;
    }

    void brake() {
        speed -= 10;
        cout << brand << " slowed down to " << speed << " km/h" << endl;
    }
};

int main() {
    Car car1("Toyota", 50);
    car1.accelerate();
    car1.brake();
    return 0;
}
```

📌 **Explanation:**

* `Car` is a class.
* `car1` is an object of the class.
* It encapsulates data and behavior together.

---

## ✅ **Advantages of OOP over Procedural Programming**

---

### 🟩 **Definition**

Procedural programming is a paradigm that relies on procedures (functions) and a sequence of steps.
OOP, on the other hand, organizes code using **objects and classes**.

---

### 🟦 **Concept**

| Feature            | Procedural                 | Object-Oriented                        |
| ------------------ | -------------------------- | -------------------------------------- |
| Structure          | Function-based             | Object-based                           |
| Data               | Global or passed manually  | Encapsulated within objects            |
| Reusability        | Harder to reuse            | Code reuse through inheritance         |
| Security           | Low (data can be modified) | High (data encapsulation)              |
| Modularity         | Poor                       | Strong modularity                      |
| Real-world Mapping | Indirect                   | Direct (objects = real-world entities) |

---

### 🟨 **Practical Use Case**

🎮 **Example: Game Development**

* **Procedural:** Managing player health, position, actions through multiple scattered functions and global variables.
* **OOP:** Define `Player` class that encapsulates `health`, `position`, `move()` and `attack()` methods.

This makes game state more organized and scalable.

---

### 🟧 **Code Comparison in C++**

#### Procedural Style

```cpp
int speed = 0;

void accelerate() {
    speed += 10;
}

void brake() {
    speed -= 10;
}
```

#### OOP Style

```cpp
class Car {
private:
    int speed;

public:
    Car() : speed(0) {}

    void accelerate() {
        speed += 10;
    }

    void brake() {
        speed -= 10;
    }
};
```

---

## ✅ **Key OOP Principles (Brief Overview)**

🔒 We will not go in-depth into these now but just introduce them.

1. **Abstraction** – Hiding internal details and showing only necessary features.
2. **Encapsulation** – Wrapping data and code together and restricting access.
3. **Inheritance** – Acquiring properties of one class into another.
4. **Polymorphism** – Performing a task in many forms (method overloading, overriding).

We will cover these in depth later.

---

## ✅ **Interview & Exam Questions (with Answers)**

---

### 🔹 **Basic + Conceptual**

1. **Q:** What is the main difference between a class and an object?

   * **A:** A class is a blueprint, and an object is an instance of the class. Class defines properties and behaviors, while the object holds actual values.

2. **Q:** Why is OOP considered closer to real-world modeling?

   * **A:** Because it allows programmers to represent real-world entities (e.g., Car, Person) as objects with properties and behaviors.

3. **Q:** Can we achieve OOP principles in C?

   * **A:** Partially. You can mimic some OOP concepts like encapsulation using structs and function pointers, but C is not fully object-oriented.

4. **Q:** Is OOP always better than procedural programming?

   * **A:** Not always. For small, straightforward tasks, procedural is simpler and faster. OOP is more beneficial in large and complex applications.

---

### 🔹 **Tricky / Creative Interview Questions**

5. **Q:** If everything is an object, is the `main()` function also an object?

   * **A:** No. `main()` is a function and not an object. Not everything in OOP must be an object; static contexts like `main()` can exist.

6. **Q:** How does OOP help in reducing bugs and improving maintainability?

   * **A:** Encapsulation hides internal states, reducing unintended interference. Inheritance and modular design reduce code duplication. Polymorphism allows flexible code extensions.

7. **Q:** Can we use OOP in a procedural language like C?

   * **A:** You can simulate OOP behavior using structs, pointers to functions, and manual abstraction, but it lacks built-in OOP features like inheritance and polymorphism.

8. **Q:** What’s the difference between an object and a reference to an object?

   * **A:** An object is the actual data instance in memory. A reference is an alias or pointer to that object. Modifying through reference affects the original object.

9. **Q:** Is it possible for two different classes to have objects with the same name?

   * **A:** Yes. Object names are scoped locally. `ClassA a; ClassB a;` would not compile in the same scope, but inside different scopes or classes, it’s valid.

10. **Q:** How would you refactor a procedural legacy codebase into OOP?

* **A:** Identify logical groupings of data and functions. Create classes encapsulating this logic. Replace global data with member variables. Gradually introduce inheritance and polymorphism for extensibility.

11. **Q:** What happens internally when an object is created in C++?

* **A:** Memory is allocated on heap or stack depending on declaration. Constructors initialize values. Virtual function table (vtable) is set up for polymorphic classes.

12. **Q:** Can we say OOP supports multiple programming paradigms?

* **A:** Yes. Most OOP languages like C++ support procedural, generic, and functional paradigms along with object-orientation.

13. **Q:** Why is OOP preferred in large-scale projects?

* **A:** OOP improves modularity, reduces redundancy, makes code more maintainable and scalable, and aligns better with team-based development.

14. **Q:** What if a class has only private data and no methods. Is it still OOP?

* **A:** Technically it’s a class, but it violates encapsulation as behavior is missing. A good OOP design requires both data and behavior to be encapsulated.

15. **Q:** What is meant by “everything is an object” in OOP?

* **A:** In pure OOP languages like Smalltalk, everything, including functions and classes, is treated as objects. In C++, this is not strictly true (e.g., primitive types).

---
