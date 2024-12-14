# SQL Comprehensive Language Guide

## 1. Database and SQL Fundamentals

### 1.1 What is SQL?
SQL (Structured Query Language) is a standardized language for managing and manipulating relational databases. It allows users to:
- Create database structures
- Insert data
- Update data
- Delete data
- Query and retrieve data

### 1.2 Database Concepts
- Tables
- Columns (Fields)
- Rows (Records)
- Primary Keys
- Foreign Keys
- Relationships

## 2. Basic SQL Syntax

### 2.1 Data Definition Language (DDL)

#### CREATE Commands
```sql
-- Create Database
CREATE DATABASE database_name;

-- Create Table
CREATE TABLE table_name (
    column1 datatype1 constraints,
    column2 datatype2 constraints,
    ...
);

-- Example
CREATE TABLE Employees (
    EmployeeID INT PRIMARY KEY,
    FirstName VARCHAR(50),
    LastName VARCHAR(50),
    Department VARCHAR(50)
);
```

#### ALTER Commands
```sql
-- Add Column
ALTER TABLE table_name
ADD column_name datatype;

-- Modify Column
ALTER TABLE table_name
MODIFY column_name new_datatype;

-- Drop Column
ALTER TABLE table_name
DROP COLUMN column_name;
```

#### DROP and TRUNCATE
```sql
-- Drop Table
DROP TABLE table_name;

-- Truncate Table (removes all data)
TRUNCATE TABLE table_name;
```

### 2.2 Data Manipulation Language (DML)

#### INSERT
```sql
-- Insert single row
INSERT INTO table_name (column1, column2)
VALUES (value1, value2);

-- Insert multiple rows
INSERT INTO table_name (column1, column2)
VALUES 
    (value1, value2),
    (value3, value4);
```

#### UPDATE
```sql
-- Update specific rows
UPDATE table_name
SET column1 = value1, column2 = value2
WHERE condition;
```

#### DELETE
```sql
-- Delete specific rows
DELETE FROM table_name
WHERE condition;

-- Delete all rows
DELETE FROM table_name;
```

## 3. SELECT Queries

### 3.1 Basic SELECT
```sql
-- Select all columns
SELECT * FROM table_name;

-- Select specific columns
SELECT column1, column2 FROM table_name;

-- Select with condition
SELECT * FROM table_name
WHERE condition;
```

### 3.2 Advanced SELECT Clauses

#### ORDER BY
```sql
-- Sort in ascending order
SELECT * FROM table_name
ORDER BY column1 ASC;

-- Sort in descending order
SELECT * FROM table_name
ORDER BY column1 DESC;
```

#### GROUP BY
```sql
-- Group and aggregate
SELECT department, COUNT(*) as employee_count
FROM employees
GROUP BY department;
```

#### HAVING
```sql
-- Filter grouped results
SELECT department, AVG(salary) as avg_salary
FROM employees
GROUP BY department
HAVING AVG(salary) > 50000;
```

## 4. JOIN Operations

Joins in SQL are used to combine rows from two or more tables based on a related column. There are several types of joins, each serving a specific purpose.

---

### 1. INNER JOIN
- Returns only the rows where there is a match in **both tables**.
- Syntax:
  ```sql
  SELECT column1, column2
  FROM table1
  INNER JOIN table2
  ON table1.common_column = table2.common_column;
  ```
- Example:
  ```sql
  SELECT employees.name, departments.name
  FROM employees
  INNER JOIN departments
  ON employees.department_id = departments.id;
  ```

---

### 2. LEFT JOIN (or LEFT OUTER JOIN)
- Returns all rows from the **left table**, and the matched rows from the right table. If no match, NULL is returned for the right table's columns.
- Syntax:
  ```sql
  SELECT column1, column2
  FROM table1
  LEFT JOIN table2
  ON table1.common_column = table2.common_column;
  ```
- Example:
  ```sql
  SELECT employees.name, departments.name
  FROM employees
  LEFT JOIN departments
  ON employees.department_id = departments.id;
  ```

---

### 3. RIGHT JOIN (or RIGHT OUTER JOIN)
- Returns all rows from the **right table**, and the matched rows from the left table. If no match, NULL is returned for the left table's columns.
- Syntax:
  ```sql
  SELECT column1, column2
  FROM table1
  RIGHT JOIN table2
  ON table1.common_column = table2.common_column;
  ```
- Example:
  ```sql
  SELECT employees.name, departments.name
  FROM employees
  RIGHT JOIN departments
  ON employees.department_id = departments.id;
  ```

---

### 4. FULL JOIN (or FULL OUTER JOIN)
- Returns rows when there is a match in **either table**.
- Non-matching rows will have NULL for the columns of the table without a match.
- Syntax:
  ```sql
  SELECT column1, column2
  FROM table1
  FULL JOIN table2
  ON table1.common_column = table2.common_column;
  ```
- Example:
  ```sql
  SELECT employees.name, departments.name
  FROM employees
  FULL JOIN departments
  ON employees.department_id = departments.id;
  ```

---

### 5. CROSS JOIN
- Returns the Cartesian product of the two tables (i.e., every row of the first table paired with every row of the second table).
- Syntax:
  ```sql
  SELECT column1, column2
  FROM table1
  CROSS JOIN table2;
  ```
- Example:
  ```sql
  SELECT employees.name, departments.name
  FROM employees
  CROSS JOIN departments;
  ```

---

### 6. SELF JOIN
- Joins a table with itself.
- Requires aliasing the table to differentiate the "left" and "right" sides of the join.
- Syntax:
  ```sql
  SELECT a.column1, b.column2
  FROM table_name a
  INNER JOIN table_name b
  ON a.common_column = b.common_column;
  ```
- Example:
  ```sql
  SELECT e1.name AS Employee, e2.name AS Manager
  FROM employees e1
  INNER JOIN employees e2
  ON e1.manager_id = e2.id;
  ```

---

## Diagram Overview
- **INNER JOIN**: Intersection of two tables.
- **LEFT JOIN**: All from left + matching from right.
- **RIGHT JOIN**: All from right + matching from left.
- **FULL JOIN**: All rows from both tables.

```plaintext
Table1:    A B C   Table2:    X Y
INNER JOIN: A B     LEFT JOIN: A B (NULL)
RIGHT JOIN: (NULL)  X Y     FULL JOIN: A B X Y


## 5. Advanced Query Techniques

### 5.1 Subqueries
```sql
-- Subquery in WHERE clause
SELECT * FROM employees
WHERE salary > (
    SELECT AVG(salary) FROM employees
);
```

### 5.2 Window Functions
```sql
-- Rank employees within department
SELECT 
    name,
    department,
    RANK() OVER (PARTITION BY department ORDER BY salary DESC) as salary_rank
FROM employees;
```

## 6. Indexes and Performance

### 6.1 Creating Indexes
```sql
-- Create single column index
CREATE INDEX index_name
ON table_name (column_name);

-- Create composite index
CREATE INDEX index_name
ON table_name (column1, column2);
```

## 7. Transaction Management

### 7.1 ACID Properties
- Atomicity
- Consistency
- Isolation
- Durability

### 7.2 Transaction Commands
```sql
-- Begin Transaction
BEGIN TRANSACTION;

-- Commit Transaction
COMMIT;

-- Rollback Transaction
ROLLBACK;
```

## 8. Data Types

### 8.1 Common SQL Data Types
- INTEGER
- DECIMAL
- VARCHAR
- CHAR
- DATE
- TIMESTAMP
- BOOLEAN
- BLOB

## 9. Constraints

### 9.1 Types of Constraints
- PRIMARY KEY
- FOREIGN KEY
- UNIQUE
- NOT NULL
- CHECK
- DEFAULT

## 10. Views
```sql
-- Create View
CREATE VIEW view_name AS
SELECT column1, column2
FROM table_name
WHERE condition;
```

## 11. Common Interview Questions

### 11.1 Theoretical Questions
1. Explain ACID properties
2. Difference between WHERE and HAVING
3. Types of Indexes
4. Normalization levels

### 11.2 Practical Queries
1. Find nth highest salary
2. Remove duplicate records
3. Pivot table transformation
4. Complex joins and subqueries

## 12. Best Practices
- Use indexing wisely
- Avoid SELECT *
- Write efficient joins
- Use prepared statements
- Normalize database design
- Handle NULL values carefully

## 13. Database-Specific Variations
- MySQL
- PostgreSQL
- SQL Server
- Oracle
- SQLite

## Conclusion
SQL is a powerful language requiring continuous practice and deep understanding of database principles.

## Recommended Learning Resources
- W3Schools SQL Tutorial
- LeetCode SQL problems
- SQL performance tuning courses
- Database design books