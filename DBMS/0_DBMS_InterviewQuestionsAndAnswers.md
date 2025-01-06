### **Basic Level**

1. **What is data?**  
   Data refers to raw facts and figures that are collected and stored. For example, names, numbers, dates, and measurements. Data becomes information when it is processed and organized.  

2. **What is a database? How is it different from a file system?**  
   A database is an organized collection of data that can be accessed, managed, and updated efficiently.  
   **Differences:**  
   - **Database:** Uses structured query languages (SQL), provides ACID properties, supports multiple users concurrently, and is highly scalable.  
   - **File System:** Stores data in flat files; has no built-in query language or ACID compliance.  

3. **What is a DBMS? List its advantages.**  
   A Database Management System (DBMS) is software that allows users to store, retrieve, and manipulate data in databases.  
   **Advantages:**  
   - Data abstraction and independence  
   - Data security and integrity  
   - Efficient data retrieval  
   - Concurrency control  

4. **What are the types of databases (hierarchical, relational, etc.)?**  
   - **Hierarchical Database:** Data is organized in a tree-like structure.  
   - **Network Database:** Data is organized as graphs with many-to-many relationships.  
   - **Relational Database:** Data is stored in tables (rows and columns).  
   - **Object-Oriented Database:** Data is represented as objects, like in OOP.  

5. **What is the difference between DBMS and RDBMS?**  
   - **DBMS:** Manages data without relationships (e.g., file-based systems).  
   - **RDBMS:** Manages data with relationships using tables, enforcing ACID properties.  

6. **Define the terms: Table, Row, Column, and Field.**  
   - **Table:** A collection of related data organized in rows and columns.  
   - **Row (Record):** A single entry in a table representing one entity.  
   - **Column (Attribute):** A vertical set of data representing a specific property.  
   - **Field:** The intersection of a row and column (a specific data value).  

7. **What is a primary key? Why is it important?**  
   A primary key uniquely identifies each row in a table. It ensures no duplicate or null values.  

8. **What is a foreign key? Explain with an example.**  
   A foreign key in one table refers to the primary key in another table to maintain referential integrity.  
   **Example:** In an Orders table, the `CustomerID` column can be a foreign key referencing the `ID` column in a Customers table.  

9. **What is a candidate key, and how is it different from a superkey?**  
   - **Candidate Key:** Minimal set of attributes that can uniquely identify a row.  
   - **Superkey:** Any set of attributes that uniquely identify a row (may contain extra attributes).  

10. **What is the difference between a unique key and a primary key?**  
    - **Primary Key:** One per table; cannot be null.  
    - **Unique Key:** Can have multiple unique keys; allows one null value.  

11. **What are constraints in DBMS? List and explain the types.**  
    Constraints enforce rules on data in tables.  
    **Types:**  
    - **NOT NULL:** Ensures a column cannot have null values.  
    - **UNIQUE:** Ensures all values in a column are distinct.  
    - **PRIMARY KEY:** Combines NOT NULL and UNIQUE.  
    - **FOREIGN KEY:** Maintains referential integrity.  
    - **CHECK:** Ensures values satisfy a condition.  

12. **What is normalization? Why is it needed?**  
    Normalization is the process of organizing data to reduce redundancy and improve integrity. It eliminates anomalies like insertion, deletion, and update anomalies.  

13. **What are the normal forms in DBMS?**  
    - **1NF:** Ensures atomic values (no repeating groups).  
    - **2NF:** Ensures 1NF + no partial dependency.  
    - **3NF:** Ensures 2NF + no transitive dependency.  
    - **BCNF:** Ensures 3NF + every determinant is a candidate key.  
    - **4NF:** Ensures no multi-valued dependency.  

14. **What are the different types of relationships in DBMS?**  
    - **One-to-One (1:1):** Each entity in A maps to one entity in B.  
    - **One-to-Many (1:N):** Each entity in A maps to multiple entities in B.  
    - **Many-to-Many (M:N):** Entities in A map to multiple entities in B and vice versa.  

15. **What is a schema in a database?**  
    A schema defines the structure of a database, including tables, columns, relationships, constraints, and other database objects.  

---
### **Intermediate Level**

16. **What is SQL, and what are its types (DDL, DML, DCL, TCL)?**  
    SQL (Structured Query Language) is used to interact with databases to create, retrieve, update, and delete data.  
    **Types:**  
    - **DDL (Data Definition Language):** CREATE, ALTER, DROP  
    - **DML (Data Manipulation Language):** SELECT, INSERT, UPDATE, DELETE  
    - **DCL (Data Control Language):** GRANT, REVOKE  
    - **TCL (Transaction Control Language):** COMMIT, ROLLBACK, SAVEPOINT  

17. **What is the difference between SQL and NoSQL databases?**  
    - **SQL:** Relational, structured schema, uses SQL, suitable for complex queries (e.g., MySQL, PostgreSQL).  
    - **NoSQL:** Non-relational, schema-less, designed for unstructured data, scalable horizontally (e.g., MongoDB, Cassandra).  

18. **What is a view? How is it different from a table?**  
    A view is a virtual table based on a SQL query. It doesn’t store data physically.  
    **Differences:**  
    - **Table:** Stores data physically.  
    - **View:** Dynamic; fetches data from underlying tables.  

19. **What is an index? How does it improve performance?**  
    An index is a database object that improves query performance by allowing quick data retrieval. It works like an optimized search mechanism but can slow down data modification operations.  

20. **What are clustered and non-clustered indexes?**  
    - **Clustered Index:** Physically sorts table data based on index keys (only one per table).  
    - **Non-Clustered Index:** Stores a separate structure with pointers to table rows (multiple allowed).  

21. **What are joins in SQL? Explain the types (INNER, LEFT, RIGHT, FULL).**  
    Joins combine rows from two or more tables based on related columns.  
    **Types:**  
    - **INNER JOIN:** Returns rows with matching values in both tables.  
    - **LEFT JOIN:** Returns all rows from the left table and matching rows from the right.  
    - **RIGHT JOIN:** Returns all rows from the right table and matching rows from the left.  
    - **FULL JOIN:** Combines rows from both tables, with NULLs for unmatched rows.  

22. **What is a self-join? Give an example.**  
    A self-join is a join where a table is joined with itself.  
    **Example:** Find employees and their managers in the same table.  

23. **What is a cross join, and how is it different from an inner join?**  
    - **Cross Join:** Produces a Cartesian product of two tables (every row of A matches every row of B).  
    - **Inner Join:** Matches rows based on a condition.  

24. **Explain ACID properties of a transaction. Why are they important?**  
    - **Atomicity:** All operations in a transaction are completed or none.  
    - **Consistency:** Data remains in a valid state after a transaction.  
    - **Isolation:** Transactions execute independently.  
    - **Durability:** Changes are permanent after a commit.  
    They ensure database reliability and integrity.  

25. **What are triggers? How are they used in databases?**  
    A trigger is a procedural code executed automatically in response to specific database events (e.g., INSERT, UPDATE).  
    **Usage:** Logging changes, enforcing constraints, auditing.  

26. **What are stored procedures and functions? Highlight the differences.**  
    - **Stored Procedure:** A precompiled block of SQL that can perform operations.  
    - **Function:** A block that returns a single value.  
    **Differences:** Functions return values and are used in queries; procedures perform operations but don’t return direct values.  

27. **What is a cursor in DBMS? When should it be used?**  
    A cursor is used to process query results row by row. Use it when operations need to be performed on individual rows.  

28. **What are aggregate functions in SQL? List a few examples.**  
    Aggregate functions perform calculations on a set of values. Examples: SUM(), AVG(), COUNT(), MAX(), MIN().  

29. **What is the difference between WHERE and HAVING clauses?**  
    - **WHERE:** Filters rows before grouping.  
    - **HAVING:** Filters groups after aggregation.  

30. **Explain the concept of subqueries and correlated subqueries.**  
    - **Subquery:** A query nested within another query, executed independently.  
    - **Correlated Subquery:** Depends on the outer query; evaluated row by row.  

---

### **Advanced Level**

31. **What happens when we delete a row that is referenced by a foreign key in another table?**  
    - **If CASCADE:** The referenced rows are deleted.  
    - **If RESTRICT/NO ACTION:** The delete operation fails.  
    - **If SET NULL/DEFAULT:** The referencing column is set to NULL or a default value.  

32. **What is a deadlock in DBMS? How can it be resolved?**  
    Deadlock occurs when two or more transactions wait for each other’s resources indefinitely.  
    **Resolution:** Deadlock detection, timeout, or prevention techniques (e.g., resource ordering).  

33. **What are the differences between OLTP and OLAP?**  
    - **OLTP:** Real-time processing, frequent updates (e.g., banking systems).  
    - **OLAP:** Analytical processing, infrequent updates (e.g., data warehousing).  

34. **What is database partitioning? What are its types?**  
    Partitioning divides a database into smaller, manageable parts.  
    **Types:** Horizontal, vertical, range, hash.  

35. **What is database sharding? How is it different from partitioning?**  
    Sharding is horizontal partitioning across multiple servers for scalability, whereas partitioning happens within a single database instance.  

36. **What is a materialized view? How is it different from a regular view?**  
    - **Materialized View:** Stores query results physically.  
    - **Regular View:** Fetches results dynamically from base tables.  

37. **How does indexing affect database performance? Can it ever degrade performance?**  
    Indexing improves read performance but can degrade write performance due to maintenance of index structures.  

38. **What is a transaction log in DBMS? Why is it important?**  
    A transaction log records all changes made to a database for recovery and rollback in case of failures.  

39. **What are isolation levels in transactions? Explain their types.**  
    Isolation levels define the degree of visibility of data changes during concurrent transactions:  
    - **Read Uncommitted**  
    - **Read Committed**  
    - **Repeatable Read**  
    - **Serializable**  

40. **What is the difference between DELETE, TRUNCATE, and DROP?**  
    - **DELETE:** Removes rows; can have WHERE conditions.  
    - **TRUNCATE:** Removes all rows; faster but no rollback.  
    - **DROP:** Deletes the table structure and data.  

41. **What are savepoints in a transaction? How are they used?**  
    Savepoints allow partial rollback within a transaction by marking specific points.  
    **Example:**  
    ```sql
    BEGIN TRANSACTION;
    SAVEPOINT sp1;
    -- Some operations
    ROLLBACK TO sp1;
    ```

42. **What is the difference between optimistic and pessimistic locking?**  
    - **Optimistic Locking:** Assumes minimal conflict and checks data integrity at commit time.  
    - **Pessimistic Locking:** Locks data during a transaction to prevent other transactions from accessing it.  

43. **Explain the concept of cascading in a database.**  
    Cascading defines actions to be taken on child tables when a referenced parent table row is updated or deleted.  
    **Types:** CASCADE, SET NULL, SET DEFAULT, RESTRICT, NO ACTION.  

44. **How are stored procedures optimized in large databases?**  
    - Use proper indexing.  
    - Avoid unnecessary computations and cursors.  
    - Minimize data fetched by limiting SELECT queries.  
    - Use query execution plans for performance analysis.  

45. **What is the role of a database administrator (DBA)?**  
    - Managing database storage and structure.  
    - Monitoring and optimizing performance.  
    - Handling backups, recovery, and security.  
    - Granting user permissions.  

---

### **Scenario-Based Questions**

46. **How would you design a database for a library management system?**  
    - Identify entities: Books, Members, Transactions, Authors.  
    - Define relationships: Books issued to Members, Books written by Authors.  
    - Use ER diagram to define tables and relationships.  
    - Normalize data to eliminate redundancy.  

47. **What is the impact of denormalization on database design? When would you choose it?**  
    Denormalization improves read performance by introducing redundancy. It is used in OLAP systems or when query performance is critical.  

48. **How would you handle a situation where a query takes too long to execute?**  
    - Check indexes on queried columns.  
    - Analyze execution plans.  
    - Optimize query structure (avoid subqueries, use joins).  
    - Partition large tables.  
    - Use caching for frequently accessed data.  

49. **Explain what happens internally when you run a SELECT query in an RDBMS.**  
    - SQL parser validates syntax.  
    - Query optimizer generates the execution plan.  
    - Data retrieval process interacts with indexes and storage.  
    - Results are returned to the user.  

50. **What steps would you take to ensure database security?**  
    - Implement user authentication and role-based access control.  
    - Encrypt sensitive data.  
    - Regularly patch and update the DBMS.  
    - Enable audit logging for activity monitoring.  
    - Restrict direct database access.  

51. **If you had to scale a database, what strategies would you use?**  
    - **Vertical Scaling:** Increase server resources (CPU, RAM).  
    - **Horizontal Scaling:** Add more servers and distribute data (sharding).  
    - Use caching mechanisms (e.g., Redis).  
    - Partition or shard data.  

52. **How would you optimize a database for a high-transaction system?**  
    - Use proper indexing.  
    - Enable connection pooling.  
    - Use faster storage systems (e.g., SSDs).  
    - Normalize only to a necessary level.  
    - Optimize queries for frequent transactions.  

53. **What would happen if an index is corrupted? How would you resolve it?**  
    Queries using the index might fail or return incorrect results.  
    **Resolution:**  
    - Drop and recreate the index.  
    - Check database logs for corruption causes.  

54. **How would you migrate data from one database to another without downtime?**  
    - Use replication to copy data to the new database.  
    - Switch the application to the new database after syncing.  
    - Perform cutover during low-traffic periods.  

55. **Explain the process of recovering a database after a crash.**  
    - Use transaction logs to roll back uncommitted changes and redo committed changes.  
    - Restore from the latest backup if needed.  
    - Apply incremental backups if available.  

---

### **Key Conceptual Questions**

56. **What are the common challenges in database management systems?**  
    - Ensuring performance at scale.  
    - Handling concurrency in transactions.  
    - Maintaining data consistency and integrity.  
    - Securing sensitive data.  

57. **How does replication work in databases? What are its advantages and disadvantages?**  
    - **Replication:** Copies data to multiple servers for redundancy and performance.  
    **Advantages:** High availability, faster reads.  
    **Disadvantages:** Potential consistency issues, increased storage costs.  

58. **What is the CAP theorem? How does it apply to distributed databases?**  
    CAP theorem states that a distributed system can only guarantee two of the three: Consistency, Availability, Partition Tolerance.  
    - Trade-offs depend on the application’s needs (e.g., CP for banking, AP for social media).  

59. **What are shadow paging and logging? How do they ensure consistency?**  
    - **Shadow Paging:** Uses a shadow copy of data pages; changes are made to a copy until committed.  
    - **Logging:** Records changes to the database for recovery purposes.  

60. **How do modern DBMS systems handle big data?**  
    - Use distributed databases like Hadoop and NoSQL solutions.  
    - Implement partitioning, replication, and parallel processing.  

61. **What are the advantages of using NoSQL databases for specific use cases?**  
    - Schema-less design for unstructured data.  
    - Scalability for large datasets.  
    - Faster read/write performance for specific use cases (e.g., IoT, social media).  

62. **Explain the concept of data warehousing and its role in decision-making.**  
    Data warehousing involves consolidating data from multiple sources into a central repository for analysis. It aids in informed decision-making by providing historical and trend analysis.  

---
