# SQL (Structured Query Language)

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



# SQL | DDL, DQL, DML, DCL and TCL Commands

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

sql
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
SELECT Students.StudentName, Courses.CourseName
FROM Students
INNER JOIN Courses ON Students.StudentID = Courses.StudentID;

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

sql
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
SELECT Students.StudentName, Courses.CourseName
FROM Students
LEFT JOIN Courses ON Students.StudentID = Courses.StudentID;

---- Result ----
| StudentName | CourseName |
|-------------|------------|
| John        | Math       |
| John        | History    |
| Alice       | Science    |
| Bob         | Math       |
| Alice       | NULL       |
## 3. RIGHT JOIN (or RIGHT OUTER JOIN)  <br>
Description: Returns all records from the right table, and the matched records from the left table. The result is NULL from the left side when there is no match.

Example:

sql
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
SELECT Students.StudentName, Courses.CourseName
FROM Students
RIGHT JOIN Courses ON Students.StudentID = Courses.StudentID;

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

sql
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
SELECT Students.StudentName, Courses.CourseName
FROM Students
FULL OUTER JOIN Courses ON Students.StudentID = Courses.StudentID;

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

sql
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
SELECT Students.StudentName, Courses.CourseName
FROM Students
CROSS JOIN Courses;

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

