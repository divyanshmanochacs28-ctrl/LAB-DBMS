# DBMS Lab Experiments (1–7)
## Experiment 1: Table Creation & Operations
### Aim:
To perform DDL and DML operations on Employee table.
### Queries:
CREATE TABLE Employee_master AS SELECT * FROM Employee;
DELETE FROM Employee_master WHERE DeptNo = 10;
UPDATE Employee_master SET SAL = SAL * 1.10 WHERE DeptNo = 20;
ALTER TABLE Employee_master MODIFY SAL NUMBER(10,2);
DROP TABLE Employee_master;
### Output:
Table created, rows deleted, updated, altered, and dropped successfully.
### Result:
DDL and DML operations executed successfully.--
## Experiment 2: Retrieving Data
### Aim:
To retrieve data using SELECT queries.
### Queries:
SELECT DISTINCT JOB FROM EMPLOYEE;
SELECT * FROM EMPLOYEE WHERE DEPTNO = 30;
SELECT * FROM EMPLOYEE WHERE JOB IN ('MANAGER','CLERK') AND DEPTNO=30;
### Output:
| JOB |
|----------|
| CLERK |
| MANAGER |
| ANALYST |
### Result:
Data retrieved successfully.--
## Experiment 3: Conditions & Sorting
### Aim:
To apply conditions and sorting.
### Queries:
SELECT * FROM EMPLOYEE WHERE DEPTNO=30 ORDER BY SAL DESC;
SELECT ENAME FROM EMPLOYEE WHERE ENAME LIKE 'S%';
### Output:
| ENAME |
|-------|
| SMITH |
| SCOTT |
### Result:
Filtering and sorting applied successfully.--
## Experiment 4: String & Date Queries
### Aim:
To use string and date functions.
### Queries:
SELECT ENAME FROM EMPLOYEE WHERE ENAME LIKE '_A%';
SELECT ENAME, SAL*12 AS ANNUAL FROM EMPLOYEE;
### Output:
| ENAME | ANNUAL |
|-------|--------|
| ALLEN | 19200 |
### Result:
String and arithmetic operations successful.--
## Experiment 5: Aggregate Functions
### Aim:
To use aggregate functions.
### Queries:
SELECT COUNT(*) FROM EMPLOYEE;
SELECT MAX(SAL), MIN(SAL), AVG(SAL) FROM EMPLOYEE;
### Output:
| COUNT |
|-------|
| 14 |
### Result:
Aggregate values calculated.--
## Experiment 6: Functions & Date Operations
### Aim:
To use built-in functions.
### Queries:
SELECT ENAME, UPPER(ENAME) FROM EMPLOYEE;
SELECT SYSDATE FROM DUAL;
### Output:
| ENAME | UPPER |
|-------|-------|
| Smith | SMITH |
### Result:
Functions executed successfully.--
## Experiment 7: Advanced Queries
### Aim:
To perform advanced SQL queries.
### Queries:
SELECT MAX(SAL)-MIN(SAL) AS DIFFERENCE FROM EMPLOYEE;
SELECT DEPTNO, COUNT(*) FROM EMPLOYEE GROUP BY DEPTNO;
### Output:
| DEPTNO | COUNT |
|--------|-------|
| 10 | 3 |
| 20 | 5 |
### Result:
Advanced queries executed successfully.