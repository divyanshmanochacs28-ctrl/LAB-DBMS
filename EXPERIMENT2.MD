Experiment 1
## Table Creation and Basic DDL Operations

**Course:** UCS4001 Database Management System  
**Experiment No:** 1  
**Date:** March 18, 2026

---

## Objective
Create EMPLOYEE and DEPARTMENT tables with specified constraints and perform basic DDL operations (CREATE, INSERT, DELETE, UPDATE, ALTER, DROP).

---

## Table Structures

### EMPLOYEE Table
| Column Name | Data Type | Size  | Attributes     |
|-------------|-----------|-------|----------------|
| EMPNO       | NUMBER    | 4     | Primary Key    |
| ENAME       | VARCHAR2  | 20    | NOT NULL       |
| JOB         | VARCHAR2  | 20    |                |
| MGR         | NUMBER    | 4     |                |
| HIREDATE    | DATE      |       |                |
| SAL         | NUMBER    | 10    |                |
| COMM        | NUMBER    | 7     |                |
| DEPTNO      | NUMBER    | 2     | Foreign Key    |

### DEPARTMENT Table
| Column Name | Data Type | Size  | Attributes     |
|-------------|-----------|-------|----------------|
| DEPTNO      | NUMBER    | 2     | Primary Key    |
| DNAME       | VARCHAR2  | 15    | NOT NULL       |

---

## Sample Data

### EMPLOYEE Table (Sample Records)
| EMPNO | ENAME  | JOB      | MGR  | HIREDATE  | SAL  | COMM | DEPTNO |
|-------|--------|----------|------|-----------|------|------|--------|
| 7369  | SMITH  | CLERK    | 7902 | 17-DEC-80 | 800  |      | 20     |
| 7499  | ALLEN  | SALESMAN | 7698 | 20-FEB-81 | 1600 | 300  | 30     |
| 7521  | WARD   | SALESMAN | 7698 | 22-FEB-81 | 1250 | 300  | 30     |
| 7566  | JONES  | MANAGER  | 7839 | 02-APR-81 | 2975 |      | 20     |
| 7654  | MARTIN | SALESMAN | 7698 | 28-SEP-81 | 1250 | 1400 | 30     |
| 7698  | BLAKE  | MANAGER  | 7839 | 01-MAY-81 | 2850 |      | 30     |
| 7782  | CLARK  | MANAGER  | 7839 | 09-JUN-81 | 2450 |      | 20     |
| 7788  | SCOTT  | ANALYST  | 7566 | 09-DEC-82 | 3000 |      | 40     |
| 7839  | KING   | PRESIDENT|      | 17-NOV-81 | 5000 |      | 20     |
| 7844  | TURNER | SALESMAN | 7698 | 08-SEP-81 | 1500 | 0    | 30     |
| 7876  | ADAMS  | CLERK    | 7788 | 12-JAN-83 | 1100 |      | 20     |
| 7900  | JAMES  | CLERK    | 7698 | 03-DEC-81 | 950  |      | 30     |
| 7902  | FORD   | ANALYST  | 7566 | 03-DEC-81 | 3000 |      | 20     |
| 7934  | MILLER | CLERK    | 7782 | 23-JAN-82 | 1300 |      | 10     |

### DEPARTMENT Table
| DEPTNO | DNAME     |
|--------|-----------|
| 10     | RESEARCH  |
| 20     | ACCOUNTING|
| 30     | SALES     |
| 40     | OPERATIONS|

---

## Experiment Queries with Expected Output

### Query 1: Create EMPLOYEE MASTER table
```sql
CREATE TABLE Employeemaster AS SELECT * FROM Employee;
Output: Table created successfully with 14 records.

Query 2: Delete records where DEPTNO = 10
sql
DELETE FROM Employeemaster WHERE DEPTNO = 10;
Output: 1 row deleted (MILLER). Records left: 13.

Query 3: Update salary by 10% for DEPTNO = 20
sql
UPDATE Employeemaster SET SAL = SAL * 1.10 WHERE DEPTNO = 20;
Output: 4 rows updated (SMITH, JONES, CLARK, KING, FORD, ADAMS).

Query 4: Alter SAL column size to (10,2)
sql
ALTER TABLE Employeemaster MODIFY SAL NUMBER(10,2);
Output: Table altered successfully.

Query 5: Drop EMPLOYEE MASTER table
sql
DROP TABLE Employeemaster;
Output: Table dropped successfully.

Sample CREATE TABLE Statements
sql
-- Create DEPARTMENT table
CREATE TABLE DEPARTMENT (
    DEPTNO NUMBER(2) PRIMARY KEY,
    DNAME VARCHAR2(15) NOT NULL
);

-- Create EMPLOYEE table
CREATE TABLE EMPLOYEE (
    EMPNO NUMBER(4) PRIMARY KEY,
    ENAME VARCHAR2(20) NOT NULL,
    JOB VARCHAR2(20),
    MGR NUMBER(4),
    HIREDATE DATE,
    SAL NUMBER(10),
    COMM NUMBER(7),
    DEPTNO NUMBER(2),
    CONSTRAINT FK_DEPTNO FOREIGN KEY (DEPTNO) REFERENCES DEPARTMENT(DEPTNO)
);  