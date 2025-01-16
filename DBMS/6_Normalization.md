### Normalization and Related Concepts

---

#### **1. What is Normalization?**
**Normalization** is a systematic process of organizing data in a database to reduce redundancy and improve data integrity. It involves dividing large tables into smaller ones and defining relationships between them to eliminate anomalies (insertion, update, and deletion anomalies).

---

#### **2. Why is Normalization Needed?**
- **Reduce Redundancy:** Prevents duplicate data storage, saving space.
- **Avoid Anomalies:** Ensures consistency during insert, update, or delete operations.
- **Improve Data Integrity:** Maintains accuracy and reliability of the data.
- **Enhance Query Performance:** Optimizes database queries by minimizing data redundancy.

---

#### **3. Normal Forms with Examples**

##### **First Normal Form (1NF)**
- A table is in **1NF** if:
  1. Each column contains atomic (indivisible) values.
  2. Each column contains values of a single type.
  3. Each row is unique (a primary key is defined).

**Example (Non-1NF):**
| Student_ID | Name      | Courses       |
|------------|-----------|---------------|
| 1          | Alice     | Math, Physics |
| 2          | Bob       | Chemistry     |

**1NF Table:**
| Student_ID | Name  | Course   |
|------------|-------|----------|
| 1          | Alice | Math     |
| 1          | Alice | Physics  |
| 2          | Bob   | Chemistry|

---

##### **Second Normal Form (2NF)**
- A table is in **2NF** if:
  1. It is in 1NF.
  2. It has no **partial dependencies** (i.e., no non-prime attribute is dependent on part of a composite primary key).

**Example:**
| Order_ID | Product_ID | Product_Name | Order_Quantity |
|----------|------------|--------------|----------------|
| 1        | P1         | Pen          | 10             |
| 1        | P2         | Pencil       | 5              |

- **Composite Key:** (Order_ID, Product_ID)
- **Violation:** `Product_Name` depends only on `Product_ID`.

**2NF Table (Decomposed):**
1. **Order Table**:  
| Order_ID | Product_ID | Order_Quantity |
|----------|------------|----------------|
| 1        | P1         | 10             |
| 1        | P2         | 5              |

2. **Product Table**:  
| Product_ID | Product_Name |
|------------|--------------|
| P1         | Pen          |
| P2         | Pencil       |

---

##### **Third Normal Form (3NF)**
- A table is in **3NF** if:
  1. It is in 2NF.
  2. There are no **transitive dependencies** (a non-prime attribute should not depend on another non-prime attribute).

**Example (Non-3NF):**
| Student_ID | Name  | Dept_ID | Dept_Name |
|------------|-------|---------|-----------|
| 1          | Alice | D1      | Science   |
| 2          | Bob   | D2      | Commerce  |

- **Violation:** `Dept_Name` depends on `Dept_ID`, which in turn depends on `Student_ID`.

**3NF Table (Decomposed):**
1. **Student Table**:  
| Student_ID | Name  | Dept_ID |
|------------|-------|---------|
| 1          | Alice | D1      |
| 2          | Bob   | D2      |

2. **Department Table**:  
| Dept_ID | Dept_Name |
|---------|-----------|
| D1      | Science   |
| D2      | Commerce  |

---

##### **Boyce-Codd Normal Form (BCNF)**
- A table is in **BCNF** if:
  1. It is in 3NF.
  2. Every determinant (attribute on the left side of a functional dependency) is a candidate key.

**Example (Non-BCNF):**
| Teacher_ID | Subject    | Dept_ID |
|------------|------------|---------|
| 1          | Math       | D1      |
| 2          | Physics    | D1      |
| 3          | Chemistry  | D2      |

- **Violation:** `Subject → Dept_ID`, but `Subject` is not a candidate key.

**BCNF Table (Decomposed):**
1. **Subject Table**:  
| Subject    | Dept_ID |
|------------|---------|
| Math       | D1      |
| Physics    | D1      |
| Chemistry  | D2      |

2. **Teacher Table**:  
| Teacher_ID | Subject   |
|------------|-----------|
| 1          | Math      |
| 2          | Physics   |
| 3          | Chemistry |

---

#### **4. Difference Between 3NF and BCNF**
| Feature                     | 3NF                                    | BCNF                       |
|-----------------------------|-----------------------------------------|----------------------------|
| **Definition**              | Allows non-prime attributes to depend on non-prime attributes, as long as they don’t cause transitive dependencies. | Ensures every determinant is a candidate key. |
| **Stringency**              | Less strict compared to BCNF.          | More stringent than 3NF.   |
| **Example of Violation**    | Transitive dependencies exist.         | Non-candidate key determinant exists. |

---

#### **5. Functional Dependencies and Transitive Dependencies**
- **Functional Dependency:**  
  - Denoted as \( X \to Y \), where the value of \( X \) uniquely determines the value of \( Y \).
  - Example: `Student_ID → Name`.

- **Transitive Dependency:**  
  - Occurs when \( X \to Y \) and \( Y \to Z \), then \( X \to Z \).
  - Example: `Student_ID → Dept_ID → Dept_Name`.

---

#### **6. Denormalization**
- **Definition:**  
Denormalization is the process of combining normalized tables into fewer tables to improve query performance by reducing the number of joins. It is often used in **data warehousing** and **OLAP systems**.

- **When It Is Used:**  
  1. To optimize **read-heavy** systems.
  2. When **real-time analytics** requires faster query results.
  3. For **reporting** purposes where fewer joins are preferred.

- **Example:**  
Instead of separate `Student` and `Department` tables, a single table with all details may be used:
| Student_ID | Name  | Dept_Name |
|------------|-------|-----------|
| 1          | Alice | Science   |
| 2          | Bob   | Commerce  |

---

