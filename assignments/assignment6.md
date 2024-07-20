# Assignment 6: Employee Database an Enterprise wishes to maintain a database to automate its operations.

## Exercise: Enterprise is divided into certain departments and each department consists of employees. The following two tables describes the automation schemas Dept (deptno, dname, loc) Emp (empno, ename, job, mgr, hiredate, sal, comm, deptno)

### Task Overview

This assignment involves creating an `Emp` and `Dept` table inserting records, calculating fields, and performing various queries and updates.

## Questions and commands

### 1. Create Dept table: Dept (deptno, dname, loc)

- CREATE TABLE Dept (
  -> deptno INT PRIMARY KEY,
  -> dname VARCHAR(50),
  -> loc VARCHAR(50)
  -> );

### 2. Create Dept table: Emp (empno, ename, job, mgr, hiredate, sal, comm, deptno)

- CREATE TABLE Emp (
  -> empno INT PRIMARY KEY,
  -> ename VARCHAR(50),
  -> job VARCHAR(50),
  -> mgr INT,
  -> hiredate DATE,
  -> sal DECIMAL(10, 2),
  -> comm DECIMAL(10, 2),
  -> deptno INT,
  -> FOREIGN KEY (deptno) REFERENCES Dept(deptno),
  -> FOREIGN KEY (mgr) REFERENCES Emp(empno)
  -> );

### 3. Insert data int Dept and Emp tables

- INSERT INTO Dept (deptno, dname, loc) VALUES
  -> (10, 'HR', 'New York'),
  -> (20, 'IT', 'San Francisco'),
  -> (30, 'Finance', 'Chicago');

- INSERT INTO Emp (empno, ename, job, mgr, hiredate, sal, comm, deptno) VALUES
  -> (1, 'John Doe', 'Manager', NULL, '1994-06-15', 60000, NULL, 10),
  -> (2, 'Jane Smith', 'Analyst', 1, '1999-08-24', 50000, 500, 10),
  -> (3, 'Emily Davis', 'Clerk', 1, '2000-11-30', 40000, NULL, 10),
  -> (4, 'Michael Brown', 'Developer', NULL, '2005-12-15', 70000, NULL, 20),
  -> (5, 'Anna Johnson', 'Team Lead', 4, '2010-03-23', 80000, 1000, 20),
  -> (6, 'Chris Lee', 'Accountant', NULL, '2000-05-01', 55000, 800, 30);

### 4. Update the employee salary by 15%, whose experience is greater than 30 years

- UPDATE Emp
  -> SET sal = sal \* 1.15
  -> WHERE TIMESTAMPDIFF(YEAR, hiredate, CURDATE()) > 30;

### 5. Delete the employees, who completed 30 years of service.

-

### 6. Display the manager who is having maximum number of employees working under him?

- SELECT mgr, COUNT(\*) AS num_employees
  -> FROM Emp
  -> GROUP BY mgr
  -> ORDER BY num_employees DESC
  -> LIMIT 1;

### 7. Create a view, which contain employee names and their manager

-
