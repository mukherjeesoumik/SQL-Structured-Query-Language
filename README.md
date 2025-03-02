# SQL (Structured Query Language)
# Table of Contents

1. [ Order of execution in SQL queries ](#Order-of-execution-in-SQL-queries)
2. [SQL | DDL, DQL, DML, DCL and TCL Commands](#DDL-DQL-DML-DCL-and-TCL-Commands)
3. [Structured Query Language](#Structured-Query-Language)
4. [SUBQUERY in SQL are queries nested inside another query](#SUBQUERY-in-SQL-are-queries-nested-inside-another-query)
5. [if-else Statement](#if-else-Statement)
6. [JOIN ](#JOIN)
7.  [ANY(n) MAX AND MIN SAL](#ANY(n)-MAX-AND-MIN-SAL)

## emp

| EMPNO | ENAME  | JOB      | MGR  | HIREDATE   | SAL    | COMM   | DEPTNO |
|-------|--------|----------|------|------------|--------|--------|--------|
| 7369  | SMITH  | CLERK    | 7902 | 1980-12-17 | 800.00 | NULL   | 20     |
| 7499  | ALLEN  | SALESMAN | 7698 | 1981-02-20 | 1600.00| 300.00 | 30     |
| 7521  | WARD   | SALESMAN | 7698 | 1981-02-22 | 1250.00| 500.00 | 30     |
| 7566  | JONES  | MANAGER  | 7839 | 1981-04-02 | 2975.00| NULL   | 20     |
| 7654  | MARTIN | SALESMAN | 7698 | 1981-09-28 | 1250.00| 1400.00| 30     |
| 7698  | BLAKE  | MANAGER  | 7839 | 1981-05-01 | 2850.00| NULL   | 30     |
| 7782  | CLARK  | MANAGER  | 7839 | 1981-06-09 | 2450.00| NULL   | 10     |
| 7788  | SCOTT  | ANALYST  | 7566 | 1987-04-19 | 3000.00| NULL   | 20     |
| 7839  | KING   | PRESIDENT| NULL | 1981-11-17 | 5000.00| NULL   | 10     |
| 7844  | TURNER | SALESMAN | 7698 | 1981-09-08 | 1500.00| 0.00   | 30     |
| 7876  | ADAMS  | CLERK    | 7788 | 1987-05-23 | 1100.00| NULL   | 20     |
| 7900  | JAMES  | CLERK    | 7698 | 1981-12-03 | 950.00 | NULL   | 30     |
| 7902  | FORD   | ANALYST  | 7566 | 1981-12-03 | 3000.00| NULL   | 20     |
| 7934  | MILLER | CLERK    | 7782 | 1982-01-23 | 1300.00| NULL   | 10     |

## dept

| DEPTNO | DNAME      | LOC       |
|--------|------------|-----------|
| 10     | ACCOUNTING | NEW YORK  |
| 20     | RESEARCH   | DALLAS    |
| 30     | SALES      | CHICAGO   |
| 40     | OPERATIONS | BOSTON    |



#databse name is sqlplus 

```cs
create database sqlplus

use sqlplus

```

#emp table
```cs
CREATE TABLE emp (
    EMPNO INT PRIMARY KEY,
    ENAME VARCHAR(50),
    JOB VARCHAR(50),
    MGR INT,
    HIREDATE DATE,
    SAL DECIMAL(10, 2),
    COMM DECIMAL(10, 2),
    DEPTNO INT
);

INSERT INTO emp (EMPNO, ENAME, JOB, MGR, HIREDATE, SAL, COMM, DEPTNO) VALUES 
(7369, 'SMITH', 'CLERK', 7902, '1980-12-17', 800.00, NULL, 20),
(7499, 'ALLEN', 'SALESMAN', 7698, '1981-02-20', 1600.00, 300.00, 30),
(7521, 'WARD', 'SALESMAN', 7698, '1981-02-22', 1250.00, 500.00, 30),
(7566, 'JONES', 'MANAGER', 7839, '1981-04-02', 2975.00, NULL, 20),
(7654, 'MARTIN', 'SALESMAN', 7698, '1981-09-28', 1250.00, 1400.00, 30),
(7698, 'BLAKE', 'MANAGER', 7839, '1981-05-01', 2850.00, NULL, 30),
(7782, 'CLARK', 'MANAGER', 7839, '1981-06-09', 2450.00, NULL, 10),
(7788, 'SCOTT', 'ANALYST', 7566, '1987-04-19', 3000.00, NULL, 20),
(7839, 'KING', 'PRESIDENT', NULL, '1981-11-17', 5000.00, NULL, 10),
(7844, 'TURNER', 'SALESMAN', 7698, '1981-09-08', 1500.00, 0.00, 30),
(7876, 'ADAMS', 'CLERK', 7788, '1987-05-23', 1100.00, NULL, 20),
(7900, 'JAMES', 'CLERK', 7698, '1981-12-03', 950.00, NULL, 30),
(7902, 'FORD', 'ANALYST', 7566, '1981-12-03', 3000.00, NULL, 20),
(7934, 'MILLER', 'CLERK', 7782, '1982-01-23', 1300.00, NULL, 10);

```

#dept table

```cs

CREATE TABLE dept (
    DEPTNO INT PRIMARY KEY,
    DNAME VARCHAR(50),
    LOC VARCHAR(50)
);

INSERT INTO dept (DEPTNO, DNAME, LOC) VALUES 
(10, 'ACCOUNTING', 'NEW YORK'),
(20, 'RESEARCH', 'DALLAS'),
(30, 'SALES', 'CHICAGO'),
(40, 'OPERATIONS', 'BOSTON');

```

## Order of execution in SQL queries

```cs
FROM: Determine the data source (tables or views) to use.

JOIN: Combine data from multiple tables based on a related column.

WHERE: Filter records based on specified conditions.

GROUP BY: Aggregate data across rows that share a common attribute.

HAVING: Filter groups based on specified conditions (used with GROUP BY).

SELECT: Choose the columns to be returned.

DISTINCT: Remove duplicate rows from the result.

ORDER BY: Sort the result set.

LIMIT/OFFSET: Specify the number of rows to return and where to start.

```


# DDL-DQL-DML-DCL-and-TCL-Commands

## 1. DDL (Data Definition Language)
DDL commands are used to define and manage database structures such as tables, indexes, and schemas. They are responsible for setting up the schema and defining the data structures.

Common DDL commands:
```cs

CREATE: Used to create new tables, views, or databases.

ALTER: Used to modify existing database objects like tables.

DROP: Used to delete tables, views, or databases.

TRUNCATE: Used to remove all records from a table without deleting the table itself.


```
## 2. DQL (Data Query Language)
DQL commands are used to query the database and retrieve data. The primary command in this category is SELECT.

Common DQL command:
```cs
SELECT: Used to fetch data from one or more tables.

```

## 3. DML (Data Manipulation Language) 
DML commands are used for manipulating data in existing database objects. These commands deal with data manipulation and are responsible for the actual data stored in the database.

Common DML commands:

```cs

INSERT: Used to add new data into a table. 

UPDATE: Used to modify existing data within a table.  

DELETE: Used to remove data from a table.
```
## 4. DCL (Data Control Language)
DCL commands deal with the rights, permissions, and other controls of the database system. They are used to control access to data.

Common DCL commands:
```cs
GRANT: Used to provide users with access privileges to the database.

REVOKE: Used to remove user access privileges granted by the GRANT command.

```

## 5. TCL (Transaction Control Language)
TCL commands are used to manage transactions in the database. They ensure the integrity of data and manage changes to the database.

Common TCL commands:

```cs

COMMIT: Used to save all changes made in the current transaction.

ROLLBACK: Used to undo the changes made in the current transaction.

SAVEPOINT: Used to set a savepoint within a transaction, allowing for partial rollbacks.

SET TRANSACTION: Used to specify characteristics for the transaction.

```
# Commands:

## Data Definition Language (DDL)
Commands:

CREATE: <br>
Creates a new table, view, index, or other database objects.

```cs
CREATE TABLE employees (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100) NOT NULL,
    salary DECIMAL(10, 2),
    department VARCHAR(100)
);
```
ALTER: <br>
Modifies an existing database object.


```cs
ALTER TABLE employees ADD COLUMN hire_date DATE;
```
DROP: <br>
Deletes an existing database object.

```cs
DROP TABLE employees;
```
## Data Query Language (DQL)
Commands:

SELECT: <br>
Retrieves data from a database.

```cs
SELECT name, salary FROM employees WHERE department = 'Sales';
```
## Data Manipulation Language (DML)
Commands:

INSERT: <br>
Inserts new data into a table.

```cs
INSERT INTO employees (name, salary, department)
VALUES ('John Doe', 75000, 'Sales');
```
UPDATE: <br>
Updates existing data within a table.

```cs
UPDATE employees SET salary = 80000 WHERE id = 1;
```
DELETE: <br>
Deletes data from a table.

```cs
DELETE FROM employees WHERE id = 1;
```
## Data Control Language (DCL)
Commands:

GRANT: <br>
Grants permissions to a user.

```cs
GRANT SELECT, INSERT ON employees TO 'username'@'host';
```
REVOKE: <br>
Revokes permissions from a user.

```cs
REVOKE SELECT, INSERT ON employees FROM 'username'@'host';
```
## Transaction Control Language (TCL)
Commands:

COMMIT: <br>
Saves the transaction changes to the database.

```cs
COMMIT;
```
ROLLBACK: <br>
Undoes the transaction changes.

```cs
ROLLBACK;
```
SAVEPOINT: <br>
Sets a point within a transaction to which you can roll back.

```cs
SAVEPOINT savepoint_name;
```

# Structured Query Language

### Example 1: Simple SELECT Query
Fetch all data from the employees table.

```cs
SELECT *
FROM employees;
```
### Example 2: SELECT with WHERE Clause
Fetch all employees who are SALESMAN.

```cs
SELECT *
FROM employees
WHERE JOB = 'SALESMAN';
```
### Example 3: SELECT with ORDER BY
Fetch all employees and order them by salary in descending order.

```cs
SELECT *
FROM employees
ORDER BY SAL DESC;
```
fetch all employees and order them by salary in ascending order, you would use the ASC keyword instead of DESC. Here’s the correct query:
```cs
SELECT *
FROM employees
ORDER BY SAL ASC;
```
### Example 4: SELECT with GROUP BY and HAVING
Fetch the total salary for each department, but only include departments where the total salary is greater than 10,000.
```cs
SELECT DEPTNO, SUM(SAL) as total_salary
FROM employees
GROUP BY DEPTNO
HAVING SUM(SAL) > 10000;
```
### Example 5: SELECT with Aggregate Functions
Fetch the average salary and the count of employees in each department.

```cs
SELECT DEPTNO, AVG(SAL) as average_salary, COUNT(*) as employee_count
FROM employees
GROUP BY DEPTNO;
```
### Example 6: SELECT with LIMIT
Fetch the top 5 employees with the highest salary.

```cs
SELECT *
FROM employees
ORDER BY SAL DESC
LIMIT 5;
```
### Example 7: UPDATE Query
Update the salary of employees in the 'SALES' department by increasing it by 10%.

```cs
UPDATE employees
SET SAL = SAL * 1.10
WHERE DEPTNO = 30;
```
### Example 8: DELETE Query
Delete all employees from the 'CLERK' job.

```cs
DELETE FROM employees
WHERE JOB = 'CLERK';
```
### Example 9: Using Arithmetic Operators
Calculate the total compensation (salary + commission) for each employee.

```cs
SELECT 
    EMPNO, 
    ENAME, 
    JOB,
    SAL + COALESCE(COMM, 0) AS total_compensation
FROM 
    employees;
```
### Example 10: Using Comparison Operators
Fetch all employees where the salary is greater than 2000.

```cs
SELECT 
    EMPNO, 
    ENAME, 
    JOB,
    SAL
FROM 
    employees
WHERE 
    SAL > 2000;
```
### Example 11: Using Logical Operators
Fetch all employees who are either MANAGER or their salary is greater than 2500.

```cs
SELECT 
    EMPNO, 
    ENAME, 
    JOB,
    SAL
FROM 
    employees
WHERE 
    JOB = 'MANAGER' OR SAL > 2500;
```
### Example 12: Using String Operators
Concatenate employee name and job title.

```cs
SELECT 
    EMPNO, 
    ENAME || ' - ' || JOB AS employee_details
FROM 
    employees;
```
### Example 13: Using BETWEEN Operator
Fetch all employees whose salary is between 1000 and 3000.

```cs
SELECT 
    EMPNO, 
    ENAME, 
    JOB,
    SAL
FROM 
    employees
WHERE 
    SAL BETWEEN 1000 AND 3000;
```
### Example 14: Using IN Operator
Fetch all employees who are in department 10, 20, or 30.

```cs
SELECT 
    EMPNO, 
    ENAME, 
    JOB,
    SAL
FROM 
    employees
WHERE 
    DEPTNO IN (10, 20, 30);
```
### Example 15: Using LIKE and OR Operators
Fetch all employees whose names contain 'SMITH' or 'KING'.

```cs
SELECT *
FROM employees
WHERE ENAME LIKE '%SMITH%' OR ENAME LIKE '%KING%';
```


# SUBQUERY in SQL are queries nested inside another query


### 1. Single-row Subquery
A single-row subquery returns only one row. Example:

```cs
SELECT ENAME, JOB
FROM employees
WHERE SAL = (SELECT MAX(SAL) FROM employees);
```
Explanation: This query retrieves the name and job of the employee with the highest salary.

### 2. Multiple-row Subquery
A multiple-row subquery returns multiple rows. Example:

```cs
SELECT ENAME, JOB
FROM employees
WHERE DEPTNO IN (SELECT DEPTNO FROM employees WHERE SAL > 2500);
```
Explanation: This query retrieves the names and jobs of employees who are in departments where at least one employee earns more than 2500.

### 3. Correlated Subquery
A correlated subquery references columns from the outer query. Example:

```cs
SELECT ENAME, SAL
FROM employees e1
WHERE SAL > (SELECT AVG(SAL) FROM employees e2 WHERE e2.DEPTNO = e1.DEPTNO);
```
Explanation: This query retrieves the names and salaries of employees who earn more than the average salary in their department.

### 4. Scalar Subquery
A scalar subquery returns a single value. Example:

```cs
SELECT ENAME, SAL, (SELECT DEPTNAME FROM departments WHERE DEPTNO = e.DEPTNO) AS DEPTNAME
FROM employees e;
```
Explanation: This query retrieves the names, salaries, and department names of employees.

### 5. Subquery in the FROM Clause
A subquery can be used in the FROM clause as a derived table. Example:

```cs
SELECT DEPTNO, AVG(SAL) as avg_salary
FROM (SELECT DEPTNO, SAL FROM employees WHERE JOB = 'CLERK') sub
GROUP BY DEPTNO;
```
Explanation: This query calculates the average salary of clerks in each department.

### 6. Subquery in the SELECT Clause
A subquery can be used in the SELECT clause to return a value for each row. Example:

```cs
SELECT ENAME, SAL, (SELECT AVG(SAL) FROM employees WHERE DEPTNO = e.DEPTNO) AS dept_avg_salary
FROM employees e;
```
Explanation: This query retrieves the names, salaries, and average salary of the employees' departments.

### 7. Subquery with EXISTS
The EXISTS keyword is used to check if a subquery returns any rows. Example:

```cs
SELECT ENAME, JOB
FROM employees e
WHERE EXISTS (SELECT 1 FROM employees WHERE MGR = e.EMPNO);
```
Explanation: This query retrieves the names and jobs of employees who are managers.

### 8. Subquery with ANY and ALL
The ANY and ALL keywords are used to compare a value to any or all values in a subquery. Example with ANY:

```
SELECT ENAME, SAL
FROM employees
WHERE SAL > ANY (SELECT SAL FROM employees WHERE JOB = 'CLERK');
```
Explanation: This query retrieves the names and salaries of employees who earn more than any clerk.

### Example with ALL:

```cs
SELECT ENAME, SAL
FROM employees
WHERE SAL > ALL (SELECT SAL FROM employees WHERE JOB = 'CLERK');
```
Explanation: This query retrieves the names and salaries of employees who earn more than all clerks.





# JOIN

1. INNER JOIN with Filter <br>
-- Query: Retrieve employee details along with their department name and location, where the employee salary is greater than 2000.
```cs
SELECT e.EMPNO, e.ENAME, e.JOB, e.SAL, d.DNAME, d.LOC
FROM emp e
INNER JOIN dept d ON e.DEPTNO = d.DEPTNO
WHERE e.SAL > 2000;

```

2. LEFT JOIN with Filter <br>
-- Query: Retrieve all employees and their respective department details, including employees who don't belong to any department, where the department is 'SALES'.

```cs
SELECT e.EMPNO, e.ENAME, e.JOB, e.SAL, d.DNAME, d.LOC
FROM emp e
LEFT JOIN dept d ON e.DEPTNO = d.DEPTNO
WHERE d.DNAME = 'SALES' OR d.DNAME IS NULL;

```
3. RIGHT JOIN with Filter <br>
-- Query: Retrieve all departments and their respective employees, including departments with no employees, where the employee job is 'MANAGER'.

```cs
SELECT e.EMPNO, e.ENAME, e.JOB, e.SAL, d.DNAME, d.LOC
FROM emp e
RIGHT JOIN dept d ON e.DEPTNO = d.DEPTNO
WHERE e.JOB = 'MANAGER' OR e.JOB IS NULL;
```
4. FULL JOIN with Filter <br>
-- Query: Retrieve all employees and their respective departments, including employees without departments and departments without employees, where the department location is 'CHICAGO'.
```cs
SELECT e.EMPNO, e.ENAME, e.JOB, e.SAL, d.DNAME, d.LOC
FROM emp e
FULL OUTER JOIN dept d ON e.DEPTNO = d.DEPTNO
WHERE d.LOC = 'CHICAGO' OR d.LOC IS NULL;
```
5. SELF JOIN with Filter <br>
-- Query: Retrieve employee details along with their manager details, where the manager is 'KING'.
```cs
SELECT e1.EMPNO, e1.ENAME, e1.JOB, e2.ENAME AS MANAGER_NAME
FROM emp e1
LEFT JOIN emp e2 ON e1.MGR = e2.EMPNO
WHERE e2.ENAME = 'KING';
```

6. CROSS JOIN with Filter <br>
-- Query: Retrieve all possible combinations of employees and departments, where the employee job is 'CLERK'.

```cs
SELECT e.*, d.*
FROM emp e
CROSS JOIN dept d
WHERE e.JOB = 'CLERK';
```

# JOIN Example:

## 1. INNER JOIN  <br>
Description: Returns records that have matching values in both tables.

Example:

---- Students ----
| StudentID | StudentName |
|-----------|-------------|
| 1         | John        |
| 2         | Alice       |
| 3         | Bob         |

---- Courses ----
| CourseID | CourseName | StudentID |
|----------|------------|-----------|
| 101      | Math       | 1         |
| 102      | Science    | 2         |
| 103      | History    | 1         |
| 104      | Math       | 3         |

---- Query ----
```cs
SELECT Students.StudentName, Courses.CourseName
FROM Students
INNER JOIN Courses ON Students.StudentID = Courses.StudentID;
```
---- Result ----
| StudentName | CourseName |
|-------------|------------|
| John        | Math       |
| John        | History    |
| Alice       | Science    |
| Bob         | Math       |
## 2. LEFT JOIN (or LEFT OUTER JOIN)  <br>
Description: Returns all records from the left table, and the matched records from the right table. The result is NULL from the right side if there is no match.

Example:

---- Students ----
| StudentID | StudentName |
|-----------|-------------|
| 1         | John        |
| 2         | Alice       |
| 3         | Bob         |

---- Courses ----
| CourseID | CourseName | StudentID |
|----------|------------|-----------|
| 101      | Math       | 1         |
| 102      | Science    | 2         |
| 103      | History    | 1         |
| 104      | Math       | 3         |

---- Query ----
```cs
SELECT Students.StudentName, Courses.CourseName
FROM Students
LEFT JOIN Courses ON Students.StudentID = Courses.StudentID;
```
---- Result ----
| StudentName | CourseName |
|-------------|------------|
| John        | Math       |
| John        | History    |
| Alice       | Science    |
| Bob         | Math       |
| john        | NULL      |


## 3. RIGHT JOIN (or RIGHT OUTER JOIN)  <br>
Description: Returns all records from the right table, and the matched records from the left table. The result is NULL from the left side when there is no match.

Example:

---- Students ----
| StudentID | StudentName |
|-----------|-------------|
| 1         | John        |
| 2         | Alice       |
| 3         | Bob         |

---- Courses ----
| CourseID | CourseName | StudentID |
|----------|------------|-----------|
| 101      | Math       | 1         |
| 102      | Science    | 2         |
| 103      | History    | 1         |
| 104      | Math       | 3         |

---- Query ----
```cs
SELECT Students.StudentName, Courses.CourseName
FROM Students
RIGHT JOIN Courses ON Students.StudentID = Courses.StudentID;
```
---- Result ----
| StudentName | CourseName |
|-------------|------------|
| John        | Math       |
| John        | History    |
| Alice       | Science    |
| Bob         | Math       |
| NULL        | History    |
## 4. FULL JOIN (or FULL OUTER JOIN)  <br>
Description: Returns all records when there is a match in either left or right table. The result is NULL from one side when there is no match.

Example:

---- Students ----
| StudentID | StudentName |
|-----------|-------------|
| 1         | John        |
| 2         | Alice       |
| 3         | Bob         |

---- Courses ----
| CourseID | CourseName | StudentID |
|----------|------------|-----------|
| 101      | Math       | 1         |
| 102      | Science    | 2         |
| 103      | History    | 1         |
| 104      | Math       | 3         |

---- Query ----
```cs
SELECT Students.StudentName, Courses.CourseName
FROM Students
FULL OUTER JOIN Courses ON Students.StudentID = Courses.StudentID;
```
---- Result ----
| StudentName | CourseName |
|-------------|------------|
| John        | Math       |
| John        | History    |
| Alice       | Science    |
| Bob         | Math       |
| NULL        | History    |
## 5. CROSS JOIN <br>
Description: Returns the Cartesian product of the two tables, meaning it returns all possible combinations of rows from the two tables.

Example:

---- Students ----
| StudentID | StudentName |
|-----------|-------------|
| 1         | John        |
| 2         | Alice       |
| 3         | Bob         |

---- Courses ----
| CourseID | CourseName | StudentID |
|----------|------------|-----------|
| 101      | Math       | 1         |
| 102      | Science    | 2         |
| 103      | History    | 1         |
| 104      | Math       | 3         |

---- Query ----
```cs
SELECT Students.StudentName, Courses.CourseName
FROM Students
CROSS JOIN Courses;
```
---- Result ----
| StudentName | CourseName |
|-------------|------------|
| John        | Math       |
| John        | Science    |
| John        | History    |
| Alice       | Math       |
| Alice       | Science    |
| Alice       | History    |
| Bob         | Math       |
| Bob         | Science    |
| Bob         | History    |

## ANY(n) MAX AND MIN SAL
### MAX SAL
```cs
SELECT DISTINCT e1.sal
FROM emp e1
WHERE n = (SELECT COUNT(DISTINCT e2.sal)
           FROM emp e2
           WHERE e2.sal > e1.sal);
```
### MIN SAL
```cs
SELECT DISTINCT e1.sal
FROM emp e1
WHERE n = (SELECT COUNT(DISTINCT e2.sal)
           FROM emp e2
           WHERE e2.sal < e1.sal);
```

