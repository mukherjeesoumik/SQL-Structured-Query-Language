# SQL | DDL, DQL, DML, DCL and TCL Commands

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

Structured Query Language(SQL), as we all know, is the database language by which we can perform certain operations on the existing database. Also, we can use this language to create a database. SQL uses specific commands like Create, Drop, Insert, etc., to carry out the required tasks.
1. **DDL** – Data Definition Language
2. **DQL** – Data Query Language
3. **DML** – Data Manipulation Language
4. **DCL** – Data Control Language

#### Though many resources claim there to be another category of SQL clauses TCL – Transaction Control Language, so we will see in detail about TCL as well.

# JOIN

-- 1. INNER JOIN with Filter
-- Query: Retrieve employee details along with their department name and location, where the employee salary is greater than 2000.
```cs
SELECT e.EMPNO, e.ENAME, e.JOB, e.SAL, d.DNAME, d.LOC
FROM emp e
INNER JOIN dept d ON e.DEPTNO = d.DEPTNO
WHERE e.SAL > 2000;

```

-- 2. LEFT JOIN with Filter
-- Query: Retrieve all employees and their respective department details, including employees who don't belong to any department, where the department is 'SALES'.

```cs
SELECT e.EMPNO, e.ENAME, e.JOB, e.SAL, d.DNAME, d.LOC
FROM emp e
LEFT JOIN dept d ON e.DEPTNO = d.DEPTNO
WHERE d.DNAME = 'SALES' OR d.DNAME IS NULL;

```
-- 3. RIGHT JOIN with Filter
-- Query: Retrieve all departments and their respective employees, including departments with no employees, where the employee job is 'MANAGER'.

```cs
SELECT e.EMPNO, e.ENAME, e.JOB, e.SAL, d.DNAME, d.LOC
FROM emp e
RIGHT JOIN dept d ON e.DEPTNO = d.DEPTNO
WHERE e.JOB = 'MANAGER' OR e.JOB IS NULL;
```
-- 4. FULL JOIN with Filter
-- Query: Retrieve all employees and their respective departments, including employees without departments and departments without employees, where the department location is 'CHICAGO'.
```cs
SELECT e.EMPNO, e.ENAME, e.JOB, e.SAL, d.DNAME, d.LOC
FROM emp e
FULL OUTER JOIN dept d ON e.DEPTNO = d.DEPTNO
WHERE d.LOC = 'CHICAGO' OR d.LOC IS NULL;
```
-- 5. SELF JOIN with Filter
-- Query: Retrieve employee details along with their manager details, where the manager is 'KING'.
```cs
SELECT e1.EMPNO, e1.ENAME, e1.JOB, e2.ENAME AS MANAGER_NAME
FROM emp e1
LEFT JOIN emp e2 ON e1.MGR = e2.EMPNO
WHERE e2.ENAME = 'KING';
```

-- 6. CROSS JOIN with Filter
-- Query: Retrieve all possible combinations of employees and departments, where the employee job is 'CLERK'.
```cs
SELECT e.EMPNO, e.ENAME, d.DNAME, d.LOC
FROM emp e
CROSS JOIN dept d
WHERE e.JOB = 'CLERK';
```
