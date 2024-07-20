# Assignment 1: Employee Table Operations

## Exercise: Retrieve Records from the EMPLOYEES Table

### Task Overview

This assignment involves creating an `EMPLOYEES` table, inserting records, and performing various SQL queries to retrieve and manipulate data.

### Questions:

### 1. create an employee’s table with the following fields: (Emp_id, First_name, Last_name, Phone_No,Hire_date,Job_id,Emp_Salary,Comission_Pct,manager \_id,Department_id)

-  CREATE TABLE EMPLOYEES 
(
  -> Emp_id INT,
  -> First_name VARCHAR(50),
  -> Last_name VARCHAR(50),
  -> Phone_No VARCHAR(15),
  -> Hire_date DATE,
  -> Job_id VARCHAR(10),
  -> Emp_Salary DECIMAL(10, 2),
  -> Commission_Pct DECIMAL(5, 2),
  -> Manager_id INT,
  -> Department_id INT
  -> )

### 2. Insert five records into the table employees

-  INSERT INTO EMPLOYEES 
(Emp_id, First_name, Last_name, Phone_No, Hire_date, Job_id, Emp_Salary, Commission_Pct, Manager_id, Department_id)
  -> VALUES
  -> (1, 'John', 'Doe', '123-456-7890', '2023-01-15', 'J101', 5000.00, 10.00, 101, 60),
  -> (2, 'Jane', 'Smith', '123-456-7891', '2023-02-20', 'J102', 4800.00, 12.00, 102, 70),
  -> (3, 'Robert', 'Brown', '123-456-7892', '2023-03-10', 'J103', 4500.00, 15.00, 103, 80),
  -> (4, 'Emily', 'Austin', '123-456-7893', '2023-04-25', 'J104', 5200.00, 8.00, 104, 60),
  -> (5, 'Michael', 'Clark', '123-456-7894', '2023-05-30', 'J105', 4700.00, 11.00, 105, 70);

### 3. Display the table Employees

-  SELECT * FROM EMPLOYEES;

### 4. Find out the employee id, names, salaries of all the employees

-  SELECT Emp_id, First_name, Last_name, Emp_Salary FROM EMPLOYEES;

### 5. Find the names of the employees who have a salary greater than or equal to 4800

-  SELECT First_name, Last_name FROM EMPLOYEES WHERE Emp_Salary >= 4800;

### 6. List out the employees whose last name is ‘AUSTIN’

-  SELECT * FROM EMPLOYEES WHERE Last_name = 'AUSTIN';

### 7. Find the names of the employees who works in departments 60,70 and 80

-  SELECT First_name, Last_name FROM EMPLOYEES WHERE Department_id IN (60, 70, 80);

### 8. Display the unique Manager_Id from employees table

-  SELECT DISTINCT Manager_id FROM EMPLOYEES;
