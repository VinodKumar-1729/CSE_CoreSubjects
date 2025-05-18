

> 🔹 **Introduction to OOPs Concepts**
---

# ✅ 2. Introduction to OOPs Concepts (C++-focused)

---

## **1. What is Object-Oriented Programming (OOP)?**

### 🧾 **Definition**

Object-Oriented Programming (OOP) is a **programming paradigm** based on the concept of **"objects"**, which contain both **data (attributes)** and **functions (methods)** that operate on the data.

### 💡 **Concept**

* The goal of OOP is to **model real-world entities** like Student, Car, Account, etc., using **classes and objects**.
* Helps in **code reuse, modularity, scalability, and abstraction.**

### 🧩 **Practical Use Case**

* In a **banking system**, different accounts (Savings, Current) can be modeled as objects with shared and unique behaviors.
* Used heavily in **game development, simulations, UI frameworks**, etc.

### 🧑‍💻 **Code Example**

```cpp
#include <iostream>
using namespace std;

class BankAccount {
    string accountHolder;
    double balance;

public:
    void setDetails(string name, double amt) {
        accountHolder = name;
        balance = amt;
    }

    void display() {
        cout << "Name: " << accountHolder << ", Balance: " << balance << endl;
    }
};

int main() {
    BankAccount acc;
    acc.setDetails("Vinod", 5000.0);
    acc.display();
    return 0;
}
```

### ❓ **Exam & Interview Questions**

* **Q1:** What is the main advantage of OOP over procedural programming?

  * *Encapsulation, reusability, and abstraction.*

* **Q2:** How does OOP help in large software development?

  * *Modular structure, easier maintenance, and team collaboration.*

* **Q3:** Can OOP be used for low-level programming like device drivers?

  * *Yes, if structured well. C++ offers OOP features with low-level control.*

---

## **2. Difference Between Procedure-Oriented and Object-Oriented Programming**

### 🧾 **Definition**

| Feature     | Procedural             | Object-Oriented          |
| ----------- | ---------------------- | ------------------------ |
| Focus       | Functions (Procedures) | Objects (Data + Methods) |
| Structure   | Top-down               | Bottom-up                |
| Data        | Global/shared          | Encapsulated             |
| Reusability | Less                   | High (via classes)       |
| Example     | C                      | C++, Java                |

### 💡 **Concept**

* Procedural: You call functions and manage data separately.
* OOP: You bundle both into a single object.

### 🧩 **Use Case**

* **Procedural:** Small scripts, quick math utilities.
* **OOP:** Large applications like games, banking systems, compilers.

### 🧑‍💻 **Code Example**

#### Procedural (C-like):

```cpp
#include <iostream>
using namespace std;

string name;
double balance;

void setDetails(string n, double b) {
    name = n;
    balance = b;
}

void display() {
    cout << "Name: " << name << ", Balance: " << balance << endl;
}

int main() {
    setDetails("Vinod", 5000);
    display();
    return 0;
}
```

#### Object-Oriented:

(Already shown above.)

### ❓ **Interview Questions**

* **Q1:** Can C be considered OOP if we use structures and function pointers?

  * *No, it lacks key OOP principles like encapsulation and inheritance.*

* **Q2:** Why does OOP support scalability better?

  * *Encapsulated modules reduce code complexity and increase maintainability.*

* **Q3:** Give one disadvantage of OOP.

  * *May have a performance overhead due to abstraction and dynamic binding.*

---

## **3. Pillars of OOP (Just Overview)**

* **Encapsulation** – Wrapping data & code
* **Abstraction** – Hiding unnecessary details
* **Inheritance** – Code reuse through hierarchy
* **Polymorphism** – Same interface, different behavior

*(Detailed breakdown later as requested.)*

---

## **4. Class & Object**

### 🧾 **Definition**

* **Class**: A **user-defined blueprint** or prototype from which objects are created.
* **Object**: A **runtime instance** of a class with actual memory.

### 💡 **Concept**

* Class defines *what* a thing is; object is the *actual* thing.
* A class is just a type until instantiated.

### 🧩 **Practical Use Case**

* `Employee` class → multiple objects like `emp1`, `emp2` (data for each employee).
* Helps in managing **data consistently across the app.**

### 🧑‍💻 **Code Example**

```cpp
class Employee {
public:
    string name;
    int id;

    void show() {
        cout << "ID: " << id << ", Name: " << name << endl;
    }
};

int main() {
    Employee e1, e2;
    e1.name = "Vinod"; e1.id = 101;
    e2.name = "Kumar"; e2.id = 102;

    e1.show();
    e2.show();
    return 0;
}
```

### ❓ **Interview Questions**

* **Q1:** Can a class exist without objects?

  * *Yes, but it will be unused unless instantiated.*

* **Q2:** Where is the memory allocated for a class?

  * *Memory is allocated only when objects are created, not for class definitions.*

* **Q3:** What happens if you don’t use the access modifier in C++?

  * *Members are private by default in a class.*

---

## **5. Class Syntax in C++**

### 🧾 **Syntax**

```cpp
class ClassName {
    // private members (default)
public:
    // public members
protected:
    // protected members
};
```

### 💡 **Concept**

* `class` keyword defines a new type.
* Use access modifiers (`public`, `private`, `protected`) to control visibility.

### 🧑‍💻 **Example**

```cpp
class Student {
    int roll;
public:
    void setRoll(int r) { roll = r; }
    void getRoll() { cout << "Roll: " << roll << endl; }
};
```

---

## **6. Object Creation in C++**

### 🧾 **Syntax**

```cpp
ClassName obj;             // Stack
ClassName* ptr = new ClassName(); // Heap
```

### 💡 **Concept**

* Stack-allocated objects are automatically destroyed.
* Heap-allocated objects require manual `delete`.

### 🧑‍💻 **Example**

```cpp
Student s1;            // Static
Student* s2 = new Student(); // Dynamic

s1.setRoll(10);
s2->setRoll(20);

s1.getRoll();
s2->getRoll();

delete s2;
```

### ❓ **Interview Questions**

* **Q1:** What’s the difference between static and dynamic object creation?

  * *Static uses stack, auto-managed; dynamic uses heap, needs manual `delete`.*

* **Q2:** What happens if `delete` is not called for dynamic object?

  * *Memory leak occurs.*

---

## **7. Access Modifiers: public, private, protected**

### 🧾 **Definition**

| Modifier    | Access Level                   |
| ----------- | ------------------------------ |
| `private`   | Only within class              |
| `public`    | Accessible everywhere          |
| `protected` | Within class & derived classes |

### 💡 **Concept**

Used to **encapsulate** data and restrict access based on visibility rules.

### 🧑‍💻 **Code Example**

```cpp
class Box {
private:
    int length;

protected:
    int width;

public:
    int height;

    void setLength(int l) { length = l; }
    int getLength() { return length; }
};
```

### ❓ **Interview Questions**

* **Q1:** What is the default access modifier in a class?

  * *Private.*

* **Q2:** Can private members be accessed using object outside the class?

  * *No, only through public member functions.*

* **Q3:** What's the difference between `protected` and `private`?

  * *Protected members can be inherited; private ones cannot.*

* **Q4 (Creative):** Can we access a private variable without using public methods?

  * *Yes, via friend functions (will cover later), or hacks like pointer casting (not recommended).*

---
