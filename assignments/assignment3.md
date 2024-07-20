# Assignment 3: Rollback and Commit Commands

## Exercise: Rollback and Commit Operations on the Teacher Table

### Task Overview

This assignment involves creating a `Teacher` table, inserting records, performing salary updates with rollback and commit commands.

### Questions and commands

### 1. Create Teacher table with the following fields (Id,Name, DeptNo, Date of joining, DeptName, Location, Salary)

- CREATE TABLE Teacher (
  -> Id INT,
  -> Name VARCHAR(50),
  -> DeptNo INT,
  -> Date_of_joining DATE,
  -> DeptName VARCHAR(50),
  -> Location VARCHAR(50),
  -> Salary DECIMAL(10, 2)
  -> );

### 2. Insert five records

- INSERT INTO Teacher (Id, Name, DeptNo, Date_of_joining, DeptName, Location, Salary)
  -> VALUES
  -> (1, 'Alice Johnson', 101, '2020-01-15', 'Mathematics', 'Springfield', 50000.00),
  -> (2, 'Bob Smith', 102, '2019-06-10', 'Commerce', 'Lincoln', 48000.00),

  -> (3, 'Charlie Brown', 101, '2021-08-23', 'Mathematics', 'Madison', 52000.00),
  -> (4, 'Diana Prince', 103, '2018-11-05', 'Physics', 'Salem', 55000.00),

  -> (5, 'Eve Adams', 102, '2022-02-28', 'Commerce', 'Reno', 47000.00);

### 3. Give Increment of 25% salary for Mathematics Department.

- START TRANSACTION;
  Query OK, 0 rows affected (0.00 sec)

mysql> UPDATE Teacher
-> SET Salary = Salary \* 1.25
-> WHERE DeptName = 'Mathematics';

### 4. Perform Rollback command

- ROLLBACK;

### 5. Give Increment of 15% salary for Commerce Department

- START TRANSACTION;
  Query OK, 0 rows affected (0.00 sec)

mysql>
mysql> UPDATE Teacher
-> SET Salary = Salary \* 1.15
-> WHERE DeptName = 'Commerce';

### 6. Perform commit command

- COMMIT;
