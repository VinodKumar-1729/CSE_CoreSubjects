

### **1. Primary Key**
- **Definition**: A primary key is a unique identifier for a record in a table. It ensures that no two rows have the same value in this column (or combination of columns) and that the value is never null.
- **Key Points**:
  - A table can have only one primary key.
  - The primary key column(s) must be unique and non-null.
  - Often serves as a reference for foreign keys in other tables.
- **Example**:  
  ```sql
  CREATE TABLE Students (
      StudentID INT PRIMARY KEY,
      Name VARCHAR(50),
      Age INT
  );
  ```
  Here, `StudentID` is the primary key.

---

### **2. Candidate Key**
- **Definition**: A candidate key is any column or set of columns that can uniquely identify a record in a table. Every table can have multiple candidate keys.
- **Key Points**:
  - Candidate keys are potential primary keys.
  - Among all candidate keys, one is chosen as the primary key.
  - Candidate keys must be unique and non-null.
- **Example**:  
  For a table `Students`, both `StudentID` and `Email` could serve as candidate keys.

---

### **3. Foreign Key**
- **Definition**: A foreign key is a column or set of columns in one table that refers to the primary key in another table, establishing a relationship between the two tables.
- **Key Points**:
  - A foreign key ensures referential integrity.
  - It can have duplicate and null values unless specified otherwise.
- **Example**:  
  ```sql
  CREATE TABLE Enrollments (
      EnrollmentID INT PRIMARY KEY,
      StudentID INT,
      CourseID INT,
      FOREIGN KEY (StudentID) REFERENCES Students(StudentID)
  );
  ```
  Here, `StudentID` is a foreign key referencing the `Students` table.

---

### **4. Super Key**
- **Definition**: A super key is any set of attributes (columns) that can uniquely identify a row in a table. A super key may contain extra attributes that are not necessary for uniqueness.
- **Key Points**:
  - Every primary key is a super key, but not all super keys are primary keys.
  - Super keys include all candidate keys.
- **Example**:  
  In a table `Students`, `{StudentID, Name}`, `{StudentID}`, and `{StudentID, Age}` are all super keys.

---

### **5. Composite Key**
- **Definition**: A composite key is a primary or candidate key that consists of two or more columns used together to uniquely identify a record.
- **Key Points**:
  - Composite keys are useful when a single attribute is insufficient to ensure uniqueness.
- **Example**:  
  ```sql
  CREATE TABLE Orders (
      OrderID INT,
      ProductID INT,
      Quantity INT,
      PRIMARY KEY (OrderID, ProductID)
  );
  ```
  Here, the combination of `OrderID` and `ProductID` forms the composite key.

---

### **6. Alternate Key**
- **Definition**: An alternate key is any candidate key that is not chosen as the primary key. It acts as a backup identifier for the table.
- **Key Points**:
  - Alternate keys are unique and non-null.
- **Example**:  
  If `StudentID` is the primary key in the `Students` table, the `Email` column could serve as an alternate key.

---

### **7. Referential Integrity**
- **Definition**: Referential integrity ensures that relationships between tables remain consistent. It means that a foreign key in a table must always refer to a valid primary key in another table.
- **Key Points**:
  - Prevents orphan records (records in the child table without a corresponding record in the parent table).
  - Supported by constraints like `FOREIGN KEY` and `ON DELETE CASCADE`.
- **Example**:  
  Consider the `Students` and `Enrollments` tables:  
  - If a `StudentID` exists in the `Enrollments` table, it must exist in the `Students` table.
  ```sql
  CREATE TABLE Students (
      StudentID INT PRIMARY KEY,
      Name VARCHAR(50)
  );

  CREATE TABLE Enrollments (
      EnrollmentID INT PRIMARY KEY,
      StudentID INT,
      FOREIGN KEY (StudentID) REFERENCES Students(StudentID) ON DELETE CASCADE
  );
  ```
  - If a student is deleted from the `Students` table, their enrollments are automatically removed.

---

### **8. Foreign Key vs. Primary Key**
| **Aspect**               | **Primary Key**                                    | **Foreign Key**                               |
|--------------------------|--------------------------------------------------|----------------------------------------------|
| **Purpose**              | Uniquely identifies a record in a table.         | Establishes relationships between tables.    |
| **Uniqueness**           | Always unique and non-null.                      | Can contain duplicate or null values.        |
| **Count in Table**       | Only one primary key per table.                  | Multiple foreign keys can exist in a table.  |
| **Parent-Child Relation**| Represents the parent entity.                    | Represents the child entity.                 |

---
