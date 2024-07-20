# Assignment 5: Employee Table Operations

## Exercise: Creating and Manipulating the Employee Table

### Task Overview

This assignment involves creating an `Emp` table, inserting records, calculating fields, and performing various queries and updates.

## Questions and commands

### 1.	create an employee table with the following fields: (Emp_No,Emp_ Name, Designation, basic, DA, HRA, PF, Gross pay, Net pay)
-     CREATE TABLE Emp (
    ->        Emp_No INT,
    ->        Emp_Name VARCHAR(50),
    ->        Designation VARCHAR(50),
    ->        Basic DECIMAL(10, 2),
    ->        DA DECIMAL(10, 2),
    ->        HRA DECIMAL(10, 2),
    ->        PF DECIMAL(10, 2),
    ->        Gross_Pay DECIMAL(10, 2),
    ->        Net_Pay DECIMAL(10, 2)
    ->    );

### 2.	Insert Five Records and calculate GrossPay and NetPay.
- INSERT INTO Emp (Emp_No, Emp_Name, Designation, Basic, DA, HRA, PF, Gross_Pay, Net_Pay)
    -> VALUES
    -> (1, 'Alice Johnson', 'Manager', 20000.00, 4000.00, 3000.00, 1500.00, NULL, NULL),
    -> (2, 'Bob Smith', 'Developer', 15000.00, 3000.00, 2500.00, 1200.00, NULL, NULL),
    -> (3, 'Charlie Brown', 'Analyst', 18000.00, 3600.00, 2700.00, 1400.00, NULL, NULL),
    -> (4, 'David White', 'Tester', 12000.00, 2400.00, 1800.00, 1000.00, NULL, NULL),
    -> (5, 'Eva Green', 'HR', 17000.00, 3400.00, 2550.00, 1300.00, NULL, NULL);

### 3.	Adding column to table and Updating Attributes DA
- 

### 4.	Adding column to table and Updating Attributes HRA
-

### 5.	Adding column to table and Updating Attributes PF
-

### 6.	Adding column to table and Updating Attributes Gross Pay
- UPDATE Emp
    -> SET Gross_Pay = Basic + DA + HRA;

### 7.	Adding column to table and Updating Attributes Net Pay
- UPDATE Emp
    -> SET Net_Pay = Gross_Pay - PF;

### 8.	Display the employee table
- select * from emp;

### 9.	Display the employees whose Basic is lowest in each department.
- SELECT * FROM Emp e1
    -> WHERE Basic = (SELECT MIN(Basic) FROM Emp e2 WHERE e1.Designation = e2.Designation);

### 10.	If NetPay is less than Rs. 10,000 add Rs. 1200 as special allowance
- UPDATE Emp
    -> SET Net_Pay = Net_Pay + 1200
    -> WHERE Net_Pay < 10000;

### 11.	Display the employees whose GrossPay lies between 10,000 & 20,000
- SELECT * FROM Emp
    -> WHERE Gross_Pay BETWEEN 10000 AND 20000;

### 12.	Display all the employees who earn maximum salary.
- SELECT * FROM Emp
    -> WHERE Net_Pay = (SELECT MAX(Net_Pay) FROM Emp);
