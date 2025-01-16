### Advanced SQL: 

#### 1. **GROUP BY, HAVING, and ORDER BY Clauses**

**GROUP BY**: Groups rows sharing the same values in specified columns into summary rows. Often used with aggregate functions (e.g., COUNT, SUM, AVG).

- **Syntax**:
  ```sql
  SELECT column1, aggregate_function(column2)
  FROM table_name
  GROUP BY column1;
  ```
- **Example**:
  ```sql
  SELECT department, COUNT(*) AS employee_count
  FROM employees
  GROUP BY department;
  ```
  This groups employees by department and counts the number of employees in each.

**HAVING**: Filters groups created by `GROUP BY` based on a condition. Similar to `WHERE` but applied to aggregated data.

- **Syntax**:
  ```sql
  SELECT column1, aggregate_function(column2)
  FROM table_name
  GROUP BY column1
  HAVING aggregate_function(column2) condition;
  ```
- **Example**:
  ```sql
  SELECT department, COUNT(*) AS employee_count
  FROM employees
  GROUP BY department
  HAVING COUNT(*) > 10;
  ```
  This returns only departments with more than 10 employees.

**ORDER BY**: Sorts the result set in ascending (`ASC`) or descending (`DESC`) order.

- **Syntax**:
  ```sql
  SELECT column1, column2
  FROM table_name
  ORDER BY column1 [ASC|DESC];
  ```
- **Example**:
  ```sql
  SELECT name, salary
  FROM employees
  ORDER BY salary DESC;
  ```
  This retrieves employee names and salaries sorted by salary in descending order.

---

#### 2. **JOINS**

Joins combine rows from two or more tables based on a related column.

- **INNER JOIN**: Returns rows where there is a match in both tables.
  ```sql
  SELECT employees.name, departments.department_name
  FROM employees
  INNER JOIN departments
  ON employees.department_id = departments.id;
  ```

- **LEFT JOIN**: Returns all rows from the left table, and the matched rows from the right table (NULL if no match).
  ```sql
  SELECT employees.name, departments.department_name
  FROM employees
  LEFT JOIN departments
  ON employees.department_id = departments.id;
  ```

- **RIGHT JOIN**: Returns all rows from the right table, and the matched rows from the left table (NULL if no match).
  ```sql
  SELECT employees.name, departments.department_name
  FROM employees
  RIGHT JOIN departments
  ON employees.department_id = departments.id;
  ```

- **FULL JOIN**: Returns rows when there is a match in one of the tables. Includes unmatched rows with NULLs.
  ```sql
  SELECT employees.name, departments.department_name
  FROM employees
  FULL JOIN departments
  ON employees.department_id = departments.id;
  ```

---

#### 3. **Subqueries and Nested Queries**

Subqueries are queries within another query.

- **Example: Subquery in WHERE clause**:
  ```sql
  SELECT name
  FROM employees
  WHERE department_id = (SELECT id FROM departments WHERE department_name = 'IT');
  ```

- **Nested Queries**:
  ```sql
  SELECT name, salary
  FROM employees
  WHERE salary > (SELECT AVG(salary) FROM employees);
  ```
  This retrieves employees earning more than the average salary.

---

#### 4. **Views, Triggers, Cursors, and Stored Procedures**

**Views**: Virtual tables created using a `SELECT` query. They simplify complex queries.

- **Syntax**:
  ```sql
  CREATE VIEW view_name AS
  SELECT column1, column2
  FROM table_name
  WHERE condition;
  ```
- **Example**:
  ```sql
  CREATE VIEW high_salary_employees AS
  SELECT name, salary
  FROM employees
  WHERE salary > 50000;
  ```

**Triggers**: Automatically execute a SQL statement in response to certain events on a table.

- **Syntax**:
  ```sql
  CREATE TRIGGER trigger_name
  AFTER INSERT
  ON table_name
  FOR EACH ROW
  BEGIN
    -- Trigger logic
  END;
  ```
- **Example**:
  ```sql
  CREATE TRIGGER after_employee_insert
  AFTER INSERT ON employees
  FOR EACH ROW
  BEGIN
    INSERT INTO logs (event)
    VALUES ('New employee added');
  END;
  ```

**Cursors**: Used to iterate through a result set row by row.

- **Syntax**:
  ```sql
  DECLARE cursor_name CURSOR FOR SELECT query;
  OPEN cursor_name;
  FETCH cursor_name INTO variables;
  CLOSE cursor_name;
  ```
- **Example**:
  ```sql
  DECLARE emp_cursor CURSOR FOR SELECT name FROM employees;
  OPEN emp_cursor;
  FETCH emp_cursor INTO @emp_name;
  CLOSE emp_cursor;
  ```

**Stored Procedures**: Precompiled SQL code saved for repeated use.

- **Syntax**:
  ```sql
  CREATE PROCEDURE procedure_name (parameters)
  BEGIN
    -- Procedure logic
  END;
  ```
- **Example**:
  ```sql
  CREATE PROCEDURE get_high_salary_employees (IN threshold INT)
  BEGIN
    SELECT name, salary
    FROM employees
    WHERE salary > threshold;
  END;
  ```
