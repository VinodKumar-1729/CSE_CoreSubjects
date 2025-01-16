### **SQL (Structured Query Language)**

#### **1. SQL Overview**
SQL is a domain-specific language used to manage and manipulate relational databases. It provides commands for defining, querying, and modifying data, and managing database security and transactions.

---

### **2. SQL Categories**
SQL is divided into four primary categories:

#### **a. Data Definition Language (DDL)**  
DDL commands define and manage the structure of database objects like tables, indexes, and schemas.

**Key Commands and Examples:**
1. **CREATE:** Creates a new database object.  
   ```sql
   CREATE TABLE employees (
       id INT PRIMARY KEY,
       name VARCHAR(100),
       salary DECIMAL(10, 2)
   );
   ```
2. **DROP:** Deletes a database object permanently.  
   ```sql
   DROP TABLE employees;
   ```
3. **ALTER:** Modifies an existing database object.  
   ```sql
   ALTER TABLE employees ADD COLUMN department VARCHAR(50);
   ```
4. **TRUNCATE:** Removes all rows from a table without logging individual row deletions.  
   ```sql
   TRUNCATE TABLE employees;
   ```

**Key Notes:**
- DDL changes are auto-committed (permanent without requiring `COMMIT`).

---

#### **b. Data Manipulation Language (DML)**  
DML commands handle the data within database objects.

**Key Commands and Examples:**
1. **INSERT:** Adds new rows to a table.  
   ```sql
   INSERT INTO employees (id, name, salary) VALUES (1, 'John Doe', 50000.00);
   ```
2. **UPDATE:** Modifies existing rows.  
   ```sql
   UPDATE employees SET salary = 55000.00 WHERE id = 1;
   ```
3. **DELETE:** Removes specific rows from a table.  
   ```sql
   DELETE FROM employees WHERE id = 1;
   ```
4. **SELECT:** Retrieves data from a table.  
   ```sql
   SELECT * FROM employees;
   ```

**Key Notes:**
- DML changes must be explicitly committed using `COMMIT`, or they can be undone using `ROLLBACK`.

---

#### **c. Data Control Language (DCL)**  
DCL commands handle permissions and access to the database.

**Key Commands and Examples:**
1. **GRANT:** Provides specific permissions to users.  
   ```sql
   GRANT SELECT, INSERT ON employees TO user1;
   ```
2. **REVOKE:** Removes specific permissions from users.  
   ```sql
   REVOKE SELECT, INSERT ON employees FROM user1;
   ```

---

#### **d. Transaction Control Language (TCL)**  
TCL commands manage transactions within a database.

**Key Commands and Examples:**
1. **COMMIT:** Saves changes made in the current transaction.  
   ```sql
   COMMIT;
   ```
2. **ROLLBACK:** Undoes changes made in the current transaction.  
   ```sql
   ROLLBACK;
   ```
3. **SAVEPOINT:** Creates a rollback point within a transaction.  
   ```sql
   SAVEPOINT sp1;
   ```
4. **RELEASE SAVEPOINT:** Deletes a savepoint.  
   ```sql
   RELEASE SAVEPOINT sp1;
   ```

---

### **3. Examples of SQL Commands**

#### **DDL: CREATE, DROP, ALTER**
1. **CREATE Statement Example:**  
   ```sql
   CREATE TABLE products (
       product_id INT PRIMARY KEY,
       product_name VARCHAR(100),
       price DECIMAL(10, 2)
   );
   ```

2. **DROP Statement Example:**  
   ```sql
   DROP TABLE products;
   ```

3. **ALTER Statement Example:**  
   ```sql
   ALTER TABLE products ADD COLUMN stock_quantity INT;
   ```

---

#### **DML: INSERT, UPDATE, DELETE, SELECT**
1. **INSERT Statement Example:**  
   ```sql
   INSERT INTO products (product_id, product_name, price) 
   VALUES (1, 'Laptop', 75000.00);
   ```

2. **UPDATE Statement Example:**  
   ```sql
   UPDATE products 
   SET price = 70000.00 
   WHERE product_id = 1;
   ```

3. **DELETE Statement Example:**  
   ```sql
   DELETE FROM products 
   WHERE product_id = 1;
   ```

4. **SELECT Statement Example:**  
   ```sql
   SELECT product_name, price 
   FROM products 
   WHERE price > 50000.00;
   ```

---

### **4. Key Concepts and Notes**
- **DDL Commands:** Irreversible unless backups are maintained.
- **DML Commands:** Ensure proper transaction handling with `COMMIT` and `ROLLBACK`.
- **DCL Commands:** Essential for multi-user database environments to enforce security.
- **TCL Commands:** Provide flexibility in controlling and reverting changes during complex operations.

