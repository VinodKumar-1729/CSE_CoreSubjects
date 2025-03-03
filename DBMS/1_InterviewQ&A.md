### 1. Introduction to DBMS

#### What is a Database Management System (DBMS)?
**Definition:** A DBMS is software that enables users to store, retrieve, and manage data efficiently in a structured manner.
**Purpose:** To provide a systematic way to create, maintain, and manipulate databases.
**Example:** MySQL, PostgreSQL, Oracle, SQL Server.

#### What are the advantages of using a DBMS?
- Reduces data redundancy and inconsistency.
- Ensures data integrity and security.
- Provides concurrent access to multiple users.
- Supports data backup and recovery.
- Offers a structured way to store and retrieve data.

#### What are the different types of databases?
- **Relational Database:** Data is stored in tables (e.g., MySQL, PostgreSQL).
- **NoSQL Database:** Non-tabular storage (e.g., MongoDB, Cassandra).
- **Hierarchical Database:** Data organized in a tree structure (e.g., IBM IMS).
- **Network Database:** Data is stored as records with multiple parent-child relationships (e.g., IDMS).
- **Object-Oriented Database:** Data is stored as objects (e.g., db4o).

#### What is the difference between DBMS and RDBMS?
| Feature  | DBMS  | RDBMS  |
|----------|-------|--------|
| Structure | Stores data as files | Stores data in tables |
| Normalization | Not supported | Supported |
| Relationships | No relation between data | Uses primary & foreign keys |
| Example | File System, XML | MySQL, PostgreSQL, Oracle |

#### What are the different types of database users?
- **Database Administrator (DBA):** Manages DBMS and ensures security.
- **Application Programmer:** Develops applications using the database.
- **End User:** Accesses and interacts with the database via applications.
- **System Analyst:** Designs database architecture and requirements.

#### What is a database schema?
**Definition:** A logical structure that defines tables, attributes, and relationships in a database.
**Example:** A schema in an RDBMS defines table structures, data types, and constraints.

#### What is metadata in DBMS?
**Definition:** Data about data, which includes information about tables, columns, indexes, and constraints.
**Example:** Column names, data types, and constraints in a table.

#### What is data redundancy?
**Definition:** Unnecessary duplication of data in a database.
**Impact:** Increases storage requirements and may lead to inconsistencies.
**Solution:** Normalization reduces redundancy.

#### What are the ACID properties in DBMS?
- **Atomicity:** Ensures transactions are fully completed or fully rolled back.
- **Consistency:** Maintains database integrity before and after transactions.
- **Isolation:** Ensures concurrent transactions do not interfere with each other.
- **Durability:** Ensures committed transactions persist even after a system crash.

#### What are the different levels of data abstraction in DBMS?
- **Physical Level:** Describes how data is stored physically.
- **Logical Level:** Defines what data is stored and relationships.
- **View Level:** Provides different user perspectives.

---

### 2. Database Models

#### What are the different types of database models?
- **Hierarchical Model:** Data stored in a tree-like structure.
- **Network Model:** Data stored as records with multiple parent-child relationships.
- **Relational Model:** Data stored in tables with relationships using keys.
- **Object-Oriented Model:** Data stored as objects.

#### What is the relational model?
**Definition:** A database model where data is organized in tables (relations) with rows (tuples) and columns (attributes).
**Example:** MySQL, PostgreSQL use the relational model.

#### What is the hierarchical model?
**Definition:** Data is stored in a tree-like structure with parent-child relationships.
**Example:** IBM IMS follows a hierarchical model.

#### What is the network model?
**Definition:** A database model where data is represented using records and relationships as graphs.
**Example:** IDMS database.

#### What is the difference between the hierarchical and network models?
| Feature  | Hierarchical Model | Network Model |
|----------|------------------|--------------|
| Structure | Tree-like | Graph-like |
| Relationship | 1-to-many | Many-to-many |
| Flexibility | Less flexible | More flexible |

#### What is an entity in the relational model?
**Definition:** A real-world object with attributes stored in a table.
**Example:** A "Student" entity with attributes like ID, Name, Age.

#### What is an attribute in the relational model?
**Definition:** A property or characteristic of an entity.
**Example:** Name, Age, and ID are attributes of the Student entity.

#### What is a tuple in the relational model?
**Definition:** A single row in a table representing a record.
**Example:** A student's record (101, "Vinod", 22).

#### What is a relation in the relational model?
**Definition:** A table containing tuples with attributes.
**Example:** Student table containing multiple student records.

#### What is a primary key in the relational model?
**Definition:** A unique identifier for each tuple in a relation.
**Example:** Student_ID in a Student table.

---

### 3. Keys in DBMS

#### What are keys in DBMS?
**Definition:** Attributes or a set of attributes that help identify records uniquely in a table.

#### What is a primary key?
**Definition:** A unique key that identifies each record in a table.
**Example:** Employee_ID in an Employee table.

#### What is a candidate key?
**Definition:** A set of attributes that can uniquely identify a record, among which one is chosen as the primary key.
**Example:** (Employee_ID, Email) in an Employee table.

#### What is a super key?
**Definition:** A set of attributes that uniquely identify a tuple but may contain extra attributes.
**Example:** (Employee_ID, Name, Email) is a super key.

#### What is a foreign key?
**Definition:** A key in one table that refers to the primary key in another table.
**Example:** Department_ID in Employee table referring to Department table.

#### What is an alternate key?
**Definition:** A candidate key that is not chosen as the primary key.
**Example:** If Employee_ID is the primary key, then Email can be an alternate key.

#### What is a composite key?
**Definition:** A key formed by combining multiple attributes to uniquely identify a record.
**Example:** (Order_ID, Product_ID) in an OrderDetails table.

#### What is a unique key?
**Definition:** A key that ensures unique values but allows one NULL value.
**Example:** Email in an Employee table.

#### What is the difference between a primary key and a unique key?
| Feature | Primary Key | Unique Key |
|---------|------------|------------|
| Uniqueness | Ensures uniqueness | Ensures uniqueness |
| NULL values | Not allowed | Allowed (one NULL) |
| Number per table | Only one | Multiple |

#### Can a table have multiple primary keys?
**Answer:** No, a table can have only one primary key, but it can have multiple unique keys and candidate keys.

## **4. Normalization and Database Design**

### **1. What is Normalization in DBMS?**
**Definition:**  
Normalization is the process of organizing data in a database to reduce redundancy and improve data integrity.

**Purpose:**  
- Eliminates duplicate data.  
- Ensures data dependencies are logically stored.  
- Reduces data anomalies (insertion, update, deletion anomalies).  

**Example:**  
If a table contains repeated customer information for every order, normalization helps break it into separate tables (Customer and Orders) with relationships.

---

### **2. Why Do We Need Normalization?**
**Purpose:**  
- To minimize redundancy and avoid unnecessary storage.  
- To prevent inconsistencies in data.  
- To ensure that relationships between tables remain accurate.  
- To improve database efficiency and integrity.  

**What Happens If It Is Not Used?**  
- Data duplication leads to wasted storage.  
- Anomalies arise (inconsistent data after updates or deletions).  
- Query performance might degrade due to excessive data duplication.  

---

### **3. What Are the Different Normal Forms?**  
- **1NF (First Normal Form)** - Eliminates duplicate columns, ensures atomic values.  
- **2NF (Second Normal Form)** - Removes partial dependencies (if the table has a composite primary key).  
- **3NF (Third Normal Form)** - Eliminates transitive dependencies.  
- **BCNF (Boyce-Codd Normal Form)** - Strengthened 3NF to handle special cases.  
- **4NF (Fourth Normal Form)** - Deals with multi-valued dependencies.  
- **5NF (Fifth Normal Form)** - Breaks down further to avoid redundancy.  

---

### **4. What is 1NF (First Normal Form)?**
**Definition:**  
A table is in 1NF if:  
- It has a primary key.  
- All attributes have atomic values (no multiple values in a single column).  
- Each column contains unique data types.  

**Example:**  
| OrderID | CustomerName | Product |  
|---------|-------------|---------|  
| 101     | Alice       | Laptop, Mouse |  

🔴 **Not in 1NF** (Product column has multiple values).  
✅ **1NF Format:**  
| OrderID | CustomerName | Product |  
|---------|-------------|---------|  
| 101     | Alice       | Laptop  |  
| 101     | Alice       | Mouse   |  

---

### **5. What is 2NF (Second Normal Form)?**
**Definition:**  
A table is in 2NF if:  
- It is in 1NF.  
- It does not have partial dependencies (i.e., no attribute depends on only part of a composite primary key).  

**Example:**  
| OrderID | ProductID | CustomerName | ProductName |  
|---------|----------|-------------|-------------|  

🔴 **Not in 2NF** (CustomerName depends only on OrderID).  
✅ **2NF Format:**  
- Split into two tables: Orders (OrderID, CustomerName) and Products (ProductID, ProductName).  

---

### **6. What is 3NF (Third Normal Form)?**
**Definition:**  
A table is in 3NF if:  
- It is in 2NF.  
- It does not have transitive dependencies (i.e., non-key attributes do not depend on other non-key attributes).  

**Example:**  
| StudentID | StudentName | Department | HOD |  
|-----------|------------|------------|-----|  

🔴 **Not in 3NF** (HOD depends on Department, not StudentID).  
✅ **3NF Format:**  
- Split into Student (StudentID, StudentName, Department) and Department (Department, HOD).  

---

### **7. What is BCNF (Boyce-Codd Normal Form)?**
**Definition:**  
A stronger version of 3NF where:  
- Every determinant is a candidate key.  

**Example:**  
| Professor | Subject | Department |  
|-----------|---------|------------|  

🔴 **Not in BCNF** (A professor may teach multiple subjects, but Subject determines Department).  
✅ **BCNF Format:**  
- Break into separate tables for Professors and Subject-Department mapping.  

---

### **8. What is 4NF and 5NF?**
- **4NF (Fourth Normal Form):** Eliminates multi-valued dependencies.  
- **5NF (Fifth Normal Form):** Resolves redundancy due to join dependencies.  

---

### **9. What is Denormalization?**
**Definition:**  
Denormalization is the process of merging tables to improve performance by reducing joins.  

**Advantages:**  
- Faster query execution.  
- Simplifies complex queries.  

**Disadvantages:**  
- Increases redundancy.  
- Uses more storage space.  

---

## **5. SQL (Structured Query Language)**

### **1. What is SQL?**
**Definition:**  
SQL (Structured Query Language) is used to manage and manipulate databases.  

**Purpose:**  
- Retrieve, insert, update, and delete data.  
- Define database structure.  
- Control database access.  

---

### **2. What Are the Different Types of SQL Commands?**
- **DDL (Data Definition Language)** – `CREATE`, `ALTER`, `DROP`  
- **DML (Data Manipulation Language)** – `INSERT`, `UPDATE`, `DELETE`  
- **DCL (Data Control Language)** – `GRANT`, `REVOKE`  
- **TCL (Transaction Control Language)** – `COMMIT`, `ROLLBACK`  

---

### **3. What is the Difference Between SQL and NoSQL?**
| Feature | SQL | NoSQL |  
|---------|-----|-------|  
| Data Model | Relational (Tables) | Non-relational (Document, Key-Value, Graph, etc.) |  
| Schema | Fixed | Flexible |  
| Scalability | Vertical | Horizontal |  

---

### **4. What is the Difference Between DELETE, DROP, and TRUNCATE?**
- **DELETE:** Removes specific rows (`WHERE` condition).  
- **DROP:** Deletes the entire table.  
- **TRUNCATE:** Clears all rows but keeps table structure.  

---

### **5. What is the Difference Between HAVING and WHERE?**
- **WHERE:** Used before grouping (`GROUP BY`).  
- **HAVING:** Used after grouping to filter groups.  

---

### **6. What is the Difference Between GROUP BY and ORDER BY?**
- **GROUP BY:** Groups rows based on column values.  
- **ORDER BY:** Sorts rows in ascending/descending order.  

---

## **6. Indexing and Optimization**

### **1. What is an Index in DBMS?**
**Definition:**  
An index is a data structure that improves search performance.  

---

### **2. What Are the Types of Indexes in DBMS?**
- **Clustered Index** – Determines how rows are stored.  
- **Non-clustered Index** – Separate structure with pointers to actual data.  
- **Composite Index** – Index on multiple columns.  

---

### **3. What is Query Optimization?**
**Definition:**  
Query optimization is the process of enhancing query performance using indexing, execution plans, etc.  

---

### **4. How Does Indexing Improve Performance?**
- Reduces search time by avoiding full table scans.  
- Improves filtering and sorting speed.  

---

### **7. Transactions and Concurrency Control**  

#### **1. What is a transaction in DBMS?**  
**Definition:** A transaction is a sequence of one or more SQL operations executed as a single unit of work, ensuring data integrity.  

**Purpose:** Ensures that the database remains in a consistent state even in the event of failures.  

**Example:** Transferring money from one bank account to another involves multiple steps, which should either all succeed or all fail together.  

```sql
START TRANSACTION;
UPDATE accounts SET balance = balance - 500 WHERE account_id = 1;
UPDATE accounts SET balance = balance + 500 WHERE account_id = 2;
COMMIT;
```
---
#### **2. What are the properties of a transaction?**  
**ACID Properties:**  
- **Atomicity:** Ensures that a transaction is either fully completed or not executed at all.  
- **Consistency:** Ensures that the database remains in a valid state before and after a transaction.  
- **Isolation:** Ensures that transactions execute independently of each other.  
- **Durability:** Ensures that committed transactions persist even after system failures.  

---
#### **3. What is concurrency control?**  
**Definition:** Concurrency control ensures that multiple transactions can be executed simultaneously without conflicts, maintaining database consistency.  

**Purpose:** Prevents issues such as lost updates, dirty reads, and inconsistent retrievals.  

**Example:** Two users transferring money simultaneously should not cause incorrect balance calculations.  

---
#### **4. What is a schedule in DBMS?**  
**Definition:** A schedule is an order in which multiple transactions are executed.  

**Purpose:** Helps analyze the execution order of transactions to maintain consistency.  

---
#### **5. What are serial and non-serial schedules?**  
- **Serial Schedule:** Transactions are executed one after another, with no interleaving.  
- **Non-Serial Schedule:** Transactions are interleaved, meaning they execute concurrently.  

---
#### **6. What is a conflict serializable schedule?**  
**Definition:** A schedule is conflict serializable if it can be transformed into a serial schedule by swapping non-conflicting operations.  

**Purpose:** Ensures that concurrent transactions do not interfere with each other.  

---
#### **7. What is a view serializable schedule?**  
**Definition:** A schedule is view serializable if it produces the same final database state as a serial schedule, even if conflicts exist.  

---
#### **8. What is a deadlock in DBMS?**  
**Definition:** A deadlock occurs when two or more transactions wait indefinitely for resources held by each other.  

**Example:**  
- Transaction T1 locks Table A and waits for Table B.  
- Transaction T2 locks Table B and waits for Table A.  

---
#### **9. How can deadlocks be prevented in DBMS?**  
**Techniques:**  
- **Timeouts:** Abort transactions that wait too long.  
- **Wait-Die & Wound-Wait:** Older transactions wait, younger ones restart.  
- **Deadlock Detection & Recovery:** Periodically detect and resolve deadlocks.  
- **Resource Ordering:** Transactions acquire resources in a predefined order.  

---
#### **10. What are the different concurrency control techniques?**  
- **Locks:** Shared and Exclusive locks.  
- **Timestamp Ordering:** Assigns timestamps to transactions.  
- **Optimistic Concurrency Control:** Checks conflicts before commit.  
- **Multiversion Concurrency Control (MVCC):** Maintains multiple versions of data.  

---

### **8. Joins and Relationships**  

#### **1. What are joins in SQL?**  
**Definition:** Joins are used to combine rows from two or more tables based on a related column.  

---
#### **2. What is an INNER JOIN?**  
**Definition:** Returns only the matching rows between two tables.  

```sql
SELECT employees.name, departments.dept_name
FROM employees
INNER JOIN departments ON employees.dept_id = departments.dept_id;
```

---
#### **3. What is a LEFT JOIN?**  
**Definition:** Returns all records from the left table and matching records from the right table.  

```sql
SELECT customers.name, orders.order_id
FROM customers
LEFT JOIN orders ON customers.customer_id = orders.customer_id;
```

---
#### **4. What is a RIGHT JOIN?**  
**Definition:** Returns all records from the right table and matching records from the left table.  

---
#### **5. What is a FULL JOIN?**  
**Definition:** Returns all records when there is a match in either left or right table.  

---
#### **6. What is a CROSS JOIN?**  
**Definition:** Returns the Cartesian product of both tables (every combination).  

---
#### **7. What is a SELF JOIN?**  
**Definition:** A join where a table is joined with itself.  

```sql
SELECT a.name AS Employee, b.name AS Manager
FROM employees a
JOIN employees b ON a.manager_id = b.id;
```

---
#### **8. What is the difference between INNER JOIN and OUTER JOIN?**  
- **INNER JOIN:** Returns only matching rows.  
- **OUTER JOIN:** Returns matching and non-matching rows (LEFT, RIGHT, FULL).  

---
#### **9. What is an equi join?**  
**Definition:** A join where the condition is based on equality (`=`).  

---
#### **10. What is a natural join?**  
**Definition:** A join that automatically matches columns with the same name in both tables.  

```sql
SELECT * FROM employees NATURAL JOIN departments;
```

---

### **9. Views and Stored Procedures**  

#### **1. What is a view in SQL?**  
**Definition:** A virtual table based on a SQL query.  

---
#### **2. What are the advantages of using views?**  
- Simplifies complex queries  
- Improves security by restricting data access  
- Enhances maintainability  

---
#### **3. Can we update a view in SQL?**  
**Answer:** Yes, but only if the view is based on a single table without aggregations.  

---
#### **4. What is a materialized view?**  
**Definition:** A view that stores the query result for faster access.  

---
#### **5. What is a stored procedure?**  
**Definition:** A precompiled SQL code that can be executed multiple times.  

```sql
CREATE PROCEDURE GetEmployee()
AS
BEGIN
    SELECT * FROM employees;
END;
```

---
#### **6. What is the difference between a stored procedure and a function?**  
| Feature            | Stored Procedure | Function |
|--------------------|-----------------|----------|
| Returns a value?  | No (optional)    | Yes (must) |
| Used in SELECT?   | No               | Yes |
| Can modify DB?    | Yes              | No |

---
#### **7. What are triggers in SQL?**  
**Definition:** A trigger is an automatic action executed in response to database events.  

---
#### **8. What are the advantages of using triggers?**  
- Ensures automatic enforcement of rules  
- Reduces application code complexity  
- Provides auditing capabilities  

---
#### **9. What are the different types of triggers?**  
- **Before Trigger:** Executes before an event.  
- **After Trigger:** Executes after an event.  
- **Instead of Trigger:** Executes instead of the original event.  

---
#### **10. What is the difference between a trigger and a stored procedure?**  
| Feature       | Trigger | Stored Procedure |
|--------------|---------|-----------------|
| Execution   | Automatically | Manually |
| Invocation  | On table events | By user |

---


### **10. NoSQL Databases**  

#### **1. What is NoSQL?**  
**Definition:** NoSQL (Not Only SQL) is a type of database that provides a flexible schema, horizontal scalability, and is optimized for large-scale data storage and retrieval.  

**Purpose:** Designed to handle unstructured, semi-structured, and structured data efficiently.  

**Example:** MongoDB, Cassandra, Redis.  

---
#### **2. What are the different types of NoSQL databases?**  
- **Document-based:** Stores data as JSON-like documents (e.g., MongoDB).  
- **Key-Value Stores:** Uses key-value pairs for fast lookups (e.g., Redis).  
- **Column-Family Stores:** Organizes data in columns rather than rows (e.g., Cassandra).  
- **Graph Databases:** Stores relationships between data (e.g., Neo4j).  

---
#### **3. What is the difference between SQL and NoSQL databases?**  
| Feature        | SQL Databases | NoSQL Databases |
|---------------|--------------|----------------|
| Schema        | Fixed        | Flexible |
| Scalability   | Vertical     | Horizontal |
| Transactions  | ACID         | BASE (Eventually consistent) |
| Best for      | Structured Data | Unstructured Data |

---
#### **4. What is MongoDB?**  
**Definition:** MongoDB is a document-oriented NoSQL database that stores data in BSON (Binary JSON) format.  

**Example:**  
```json
{
  "name": "John",
  "age": 30,
  "city": "New York"
}
```

---
#### **5. What is Cassandra?**  
**Definition:** Apache Cassandra is a distributed NoSQL database that provides high availability and fault tolerance.  

**Purpose:** Ideal for handling large amounts of data across multiple nodes.  

---
#### **6. What is a document-oriented database?**  
**Definition:** A database that stores data as documents, typically in JSON or BSON format.  

---
#### **7. What is a key-value store?**  
**Definition:** A NoSQL database where data is stored as key-value pairs.  

**Example:**  
```python
store["username"] = "Vinod"
```

---
#### **8. What are the advantages of NoSQL?**  
- Flexible schema  
- High scalability  
- Fast performance for big data  
- Supports unstructured data  

---
#### **9. When should we use NoSQL over SQL?**  
- When dealing with large amounts of unstructured or semi-structured data.  
- When horizontal scaling is needed.  
- When high availability and low latency are required.  

---
#### **10. What are the disadvantages of NoSQL?**  
- No strict ACID compliance.  
- Less mature than SQL databases.  
- Limited support for complex queries.  

---

### **11. Security in DBMS**  

#### **1. What is database security?**  
**Definition:** Database security refers to the protection of databases from unauthorized access, data breaches, and corruption.  

---
#### **2. What are authentication and authorization in DBMS?**  
- **Authentication:** Verifies a user’s identity.  
- **Authorization:** Defines what actions a user is allowed to perform.  

---
#### **3. What is role-based access control (RBAC)?**  
**Definition:** A security model where access permissions are assigned based on user roles.  

---
#### **4. What are SQL injections?**  
**Definition:** A type of attack where malicious SQL code is inserted into queries to manipulate the database.  

**Example of an SQL injection attack:**  
```sql
SELECT * FROM users WHERE username = '' OR '1'='1';
```

---
#### **5. How can we prevent SQL injections?**  
- Use **prepared statements** and **parameterized queries**.  
- Validate user inputs.  
- Limit database permissions.  

---
#### **6. What is encryption in DBMS?**  
**Definition:** Encrypting sensitive data to protect it from unauthorized access.  

**Example:**  
```sql
SELECT AES_ENCRYPT('password', 'key');
```

---
#### **7. What is auditing in DBMS?**  
**Definition:** Tracking and recording database activities for security and compliance.  

---
#### **8. What are database backups?**  
**Definition:** Creating copies of the database to restore in case of data loss.  

---
#### **9. What is data masking?**  
**Definition:** Hiding sensitive data to protect privacy.  

**Example:**  
Original: `1234-5678-9101-1121` → Masked: `XXXX-XXXX-XXXX-1121`  

---
#### **10. What are firewalls in DBMS?**  
**Definition:** Firewalls protect databases by restricting unauthorized network access.  

---

### **12. Miscellaneous DBMS Questions**  

#### **1. What is a cursor in SQL?**  
**Definition:** A database object that allows row-by-row processing of query results.  

---
#### **2. What is a savepoint in SQL?**  
**Definition:** A savepoint allows rolling back part of a transaction.  

**Example:**  
```sql
SAVEPOINT sp1;
ROLLBACK TO sp1;
```

---
#### **3. What is a phantom read?**  
**Definition:** A situation where a transaction sees new rows added by another transaction after a read operation.  

---
#### **4. What is dirty read in DBMS?**  
**Definition:** When a transaction reads uncommitted changes from another transaction.  

---
#### **5. What is the difference between optimistic and pessimistic concurrency control?**  
| Type | Definition |
|------|------------|
| **Optimistic** | Assumes conflicts are rare; checks at commit time. |
| **Pessimistic** | Prevents conflicts by locking data before accessing. |

---
#### **6. What is an OLAP system?**  
**Definition:** Online Analytical Processing (OLAP) is used for complex queries and data analysis.  

---
#### **7. What is an OLTP system?**  
**Definition:** Online Transaction Processing (OLTP) handles real-time transactions.  

---
#### **8. What is data warehousing?**  
**Definition:** A system that stores historical data for analysis and reporting.  

---
#### **9. What is ETL (Extract, Transform, Load)?**  
**Definition:** A process in which data is extracted from sources, transformed into a usable format, and loaded into a data warehouse.  

---
#### **10. What are big data databases?**  
**Definition:** Databases optimized for handling large-scale, distributed data (e.g., Hadoop, Apache Spark).  

---
