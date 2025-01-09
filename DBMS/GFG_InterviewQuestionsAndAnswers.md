1. **What are the advantages of DBMS over traditional file-based systems?**
   Database management systems were developed to address the following difficulties of typical file-processing systems supported by conventional operating systems:
   - **Data Redundancy and Inconsistency**: DBMS minimizes redundancy and ensures consistency.
   - **Difficulty in Accessing Data**: DBMS provides efficient query mechanisms for accessing data.
   - **Data Isolation**: DBMS manages multiple files and formats seamlessly.
   - **Integrity Problems**: Enforces integrity constraints effectively.
   - **Atomicity of Updates**: Ensures that all updates are atomic, meaning either all or none occur.
   - **Concurrent Access by Multiple Users**: Allows safe concurrent data access.
   - **Security Problems**: Enforces robust security measures.

2. **What are super, primary, candidate, and foreign keys?**
   - **Super Key**: A set of attributes of a relation schema upon which all attributes of the schema are functionally dependent. It ensures row uniqueness.
   - **Candidate Key**: A minimal super key. No proper subset of a candidate key can be a super key.
   - **Primary Key**: A selected candidate key that uniquely identifies rows in a table. Each table has one primary key.
   - **Foreign Key**: A field (or collection of fields) in one table that uniquely identifies a row in another table.

3. **What is the difference between primary key and unique constraints?**
   - A **Primary Key** cannot have NULL values and is unique for each row in the table. There is only one primary key per table.
   - A **Unique Constraint** can have NULL values and there can be multiple unique constraints in a table.

4. **What is database normalization?**
   - A process of organizing relation schemas to minimize redundancy and anomalies (insertion, deletion, update).
   - Achieved by decomposing schemas based on functional dependencies and primary keys.

5. **Why is the use of DBMS recommended?**
   Major advantages include:
   - **Controlled Redundancy**: Reduces data duplication.
   - **Data Sharing**: Allows simultaneous data access for multiple users.
   - **Backup and Recovery Facility**: Automates data backup and recovery.
   - **Enforcement of Integrity Constraints**: Ensures data integrity.
   - **Independence of Data**: Allows changes in data structure without affecting application programs.

6. **What are the differences between DDL, DML, and DCL in SQL?**
   - **DDL (Data Definition Language)**: Includes commands like CREATE, ALTER, DROP, TRUNCATE, and RENAME.
   - **DML (Data Manipulation Language)**: Includes SELECT, INSERT, DELETE, and UPDATE.
   - **DCL (Data Control Language)**: Includes GRANT and REVOKE.

7. **What is the difference between HAVING and WHERE clauses?**
   - **WHERE Clause**: Filters rows before grouping and does not allow aggregate functions.
   - **HAVING Clause**: Filters rows after grouping and allows aggregate functions.

8. **How to print duplicate rows in a table?**
   Refer to detailed examples at: [GeeksforGeeks Article](https://www.geeksforgeeks.org/how-to-print-duplicate-rows-in-a-table/).

9. **What is a Join in SQL?**
   - Combines data from two or more tables based on a common field.
   - Example query:
     ```sql
     SELECT StudentCourse.CourseID, Student.StudentName
     FROM StudentCourse
     INNER JOIN Student
     ON StudentCourse.EnrollNo = Student.EnrollNo
     ORDER BY StudentCourse.CourseID;
     ```

10. **What is Identity in SQL?**
    - A column that auto-generates numeric values.
    - It can have a starting and increment value.

11. **What is a view in SQL? How to create a view?**
    - A virtual table based on the result-set of an SQL query.
    - Syntax:
      ```sql
      CREATE VIEW view_name AS
      SELECT column_name(s)
      FROM table_name
      WHERE condition;
      ```

12. **What are the uses of a view?**
    - Represents a subset of data for controlled exposure.
    - Joins and simplifies multiple tables.
    - Aggregates data for summaries.
    - Hides complexity and saves storage.
    - Enhances security.

13. **What is a Trigger in SQL?**
    - A code executed automatically upon insert, update, or delete operations in a table.
    - Useful for maintaining data integrity.

14. **What is a stored procedure?**
    - A compiled function containing a set of operations for common database tasks.

15. **What is the difference between Trigger and Stored Procedure?**
    - Triggers execute automatically with associated queries, while stored procedures must be called explicitly.

16. **What is a transaction? What are ACID properties?**
    - A transaction is a set of operations treated as a single unit (all or nothing).
    - **ACID Properties**:
      - **Atomicity**: Ensures all-or-nothing execution.
      - **Consistency**: Ensures the database remains in a valid state.
      - **Isolation**: Ensures transactions do not interfere with each other.
      - **Durability**: Ensures changes persist after a transaction completes.

17. **What are indexes?**
    - Data structures to improve retrieval speed.
    - Require additional storage but allow faster searches.

18. **What are clustered and non-clustered indexes?**
    - **Clustered Index**: Physically sorts data; only one allowed per table.
    - **Non-Clustered Index**: Provides logical ordering using structures like B-trees.

19. **What is Denormalization?**
    - An optimization technique where redundant data is added for faster querying.

20. **What is a Clause in SQL?**
    - A query part that filters or customizes data retrieval.

21. **What is a Live Lock?**
    - A situation where processes repeatedly interact without making progress, differing from deadlock as processes remain active but unproductive.


**21. What is QBE?**  
Query-by-Example (QBE) is a visual method of querying databases using skeleton tables as templates. It allows users to enter example values directly into these templates, simplifying database queries without needing programming knowledge.  
**Key Features:**  
- **Two-dimensional syntax:** Queries resemble tables.
- Allows intuitive query formation for personal computers and database systems.

---

**22. Why are cursors necessary in embedded SQL?**  
Cursors are used to process query results row by row in application programs.  
- SQL operates on datasets, whereas host languages handle individual rows.  
- Cursors bridge this gap, enabling navigation through query results.  
- A cursor can be thought of as a pointer to rows in a dataset.

---

**23. What is the purpose of normalization in DBMS?**  
Normalization organizes database attributes to reduce redundancy and anomalies.  
**Purpose:**  
- Removes duplicate data.  
- Divides large tables into smaller, related tables.  
- Reduces redundancy and improves consistency.  
- Minimizes anomalies during database updates.

---

**24. What is the difference between a database schema and a database state?**  
- **Database schema:** Overall design of the database.  
- **Database state:** Collection of information stored in the database at a specific time.

---

**25. What is the purpose of SQL?**  
Structured Query Language (SQL) interacts with relational databases for:  
- Inserting, updating, and deleting data.  
- Querying and managing database structures.

---

**26. Explain the concepts of Primary Key and Foreign Key.**  
- **Primary Key:** Uniquely identifies records in a table.  
- **Foreign Key:** Links tables and refers to the primary key of another table.  
**Example:**  
- Employee(ID) is a primary key in the Employee table.  
- Department(EmployeeID) uses ID as a foreign key.

---

**27. What are the main differences between Primary Key and Unique Key?**  
- **Primary Key:** Cannot have NULL values and is unique per table.  
- **Unique Key:** Can have NULL values and multiple unique keys are allowed in a table.

---

**28. What is the concept of a subquery in SQL?**  
A subquery is a query nested inside another query, often referred to as an inner query.  
**Example:**  
```sql
SELECT * FROM Employee WHERE DepartmentID IN 
  (SELECT ID FROM Department WHERE Name = 'HR');
```

---

**29. What is the use of the DROP command, and how does it differ from TRUNCATE and DELETE?**  
- **DROP:** Deletes the table and its structure permanently.  
- **TRUNCATE:** Deletes table data but retains its structure.  
- **DELETE:** Removes specific rows; can be rolled back.

---

**30. What is the main difference between UNION and UNION ALL?**  
- **UNION:** Combines results, removing duplicates.  
- **UNION ALL:** Combines results, retaining duplicates.

---

**31. What is a Correlated Subquery?**  
A correlated subquery depends on outer query values and executes row by row.  
**Example:**  
```sql
SELECT * FROM Employee E WHERE Salary > 
  (SELECT AVG(Salary) FROM Department D WHERE E.DeptID = D.ID);
```

---

**32. Explain Entity, Entity Type, and Entity Set in DBMS.**  
- **Entity:** Object with independent existence (e.g., a book).  
- **Entity Type:** Collection of entities sharing attributes (e.g., Students).  
- **Entity Set:** Group of similar entities.

---

**33. What are the different levels of abstraction in DBMS?**  
1. **Physical Level:** How data is stored.  
2. **Logical Level:** Relationships among stored data.  
3. **View Level:** Subset of database visible to users.

---

**34. What integrity rules exist in DBMS?**  
1. **Entity Integrity:** Primary keys must be unique and not NULL.  
2. **Referential Integrity:** Foreign keys must match primary keys or be NULL.

---

**35. What is the E-R model in DBMS?**  
The Entity-Relationship (E-R) model represents entities and their relationships graphically, used for designing databases.

---

**36. What is a functional dependency in DBMS?**  
A functional dependency describes how one attribute uniquely determines another.  
**Example:**  
If Y -> Z, then Z is dependent on Y.

---

**37. What is 1NF in DBMS?**  
First Normal Form (1NF):  
- Ensures atomicity (no repeating groups or arrays).  
- Removes duplicate columns in tables.

---

**38. What is 2NF in DBMS?**  
Second Normal Form (2NF):  
- A table in 1NF.  
- Non-prime attributes are fully functionally dependent on the primary key.

---

**39. What is 3NF in DBMS?**  
Third Normal Form (3NF):  
- A table in 2NF.  
- Non-prime attributes are not transitively dependent on the primary key.

---

**40. What is BCNF in DBMS?**  
Boyce-Codd Normal Form (BCNF):  
- A stricter version of 3NF.  
- Ensures every determinant is a superkey.

**41. What is a CLAUSE in SQL?**
A CLAUSE in SQL is used with queries to fetch specific data based on conditions. It helps in selecting specific records from a dataset. For example, the WHERE and HAVING clauses are commonly used.

**42. How can you get alternate records from a table in SQL?**
To fetch alternate records, use the MOD function with row numbers:
- For odd records:
  ```sql
  SELECT EmpId FROM (SELECT ROWNUM, EmpId FROM Emp) WHERE MOD(ROWNUM, 2) = 1;
  ```
- For even records:
  ```sql
  SELECT EmpId FROM (SELECT ROWNUM, EmpId FROM Emp) WHERE MOD(ROWNUM, 2) = 0;
  ```

**43. How is pattern matching done in SQL?**
Pattern matching is done using the LIKE operator:
- `%`: Matches zero or more characters.
- `_`: Matches exactly one character.

**Example:**
```sql
SELECT * FROM Emp WHERE name LIKE 'b%';  -- Names starting with 'b'
SELECT * FROM Emp WHERE name LIKE 'hans_'; -- Names starting with 'hans' and one additional character
```

**44. What is a join in SQL?**
A JOIN in SQL is used to combine rows from two or more tables based on a related column.

**45. What are the different types of joins in SQL?**
1. **Inner Join:** Returns rows with matching values in both tables.
2. **Left Join:** Returns all rows from the left table and matching rows from the right table.
3. **Right Join:** Returns all rows from the right table and matching rows from the left table.
4. **Full Join:** Returns rows from all tables; unmatched rows are filled with NULLs.

**46. Explain the Stored Procedure.**
A Stored Procedure is a collection of SQL statements with a unique name, stored in an RDBMS. It can be invoked as needed to perform a specific operation.

**47. What is RDBMS?**
RDBMS stands for Relational Database Management System. It organizes data into tables and uses common fields to establish relationships between them.

**48. What are the different types of relationships in DBMS?**
1. **One-to-One:** Each record in one table is linked to exactly one record in another table.
2. **One-to-Many:** One record in a table can be linked to multiple records in another table.
3. **Many-to-Many:** Records in two tables can have multiple associations with each other.

**49. What do you mean by Entity Type Extension?**
Entity Type Extension refers to the compilation of similar entity types into one larger entity set.

**50. What is conceptual design in DBMS?**
Conceptual design is the initial stage of database design. It focuses on creating a data model that is independent of database software or physical details, emphasizing entities, attributes, relationships, and constraints.

**51. Differentiate between logical and physical database design.**

| **Parameter**          | **Logical Database Design**                                                                                       | **Physical Database Design**                                                                                  |
|------------------------|------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
| **Task**              | Maps the conceptual schema to a relational schema.                                                               | Designs physical storage structures, record placement, and indexes.                                         |
| **Choice of Criteria**| System-independent mapping, tailored to specific DBMS.                                                           | Optimized for response time, space utilization, and transaction throughput.                                 |
| **Result**            | DDL statements for conceptual and external schemas.                                                             | Defines internal schema and determines storage structures and access paths.                                 |

**52. What are temporary tables? When are they useful?**
Temporary tables exist only during a session or transaction. They are used for specialized rollups or specific application processing. Unlike permanent tables, they allocate space dynamically. In Oracle, use:
```sql
CREATE GLOBAL TEMPORARY TABLE temp_table (...);
```

**53. Explain different types of failures in Oracle databases.**
1. **Statement Failure:** Errors like bad data types, insufficient space, or privileges.
2. **User Process Failure:** Abnormal session termination by the user.
3. **User Error:** Accidental table drops or data corruption by users.
4. **Instance Failure:** Caused by power loss or system crashes.
5. **Media Failure:** Disk corruption or failure.
6. **Alert Logs:** Logs all informational messages, errors, and instance start-ups or shutdowns.

**54. What is the main goal of RAID technology?**
RAID (Redundant Array of Independent Disks) enhances fault tolerance and performance by combining multiple disks into one logical unit. Benefits include:
- Improved fault tolerance.
- Higher throughput levels compared to single disks.
- Essential for client/server applications.
