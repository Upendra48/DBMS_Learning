# Assignment 4: Group By and Order By Clauses

## Exercise: Group By and Order By Operations on the Sales Table

### Task Overview

This assignment involves creating a `Sales` table, inserting records, and performing various queries using the `GROUP BY` and `ORDER BY` clauses.

## Questions and Commands

### 1. Create a Sales Table with the following fields (Sales_No,Sales_Name,Branch,Sales_Amount,DOB)

- CREATE TABLE Sales (
  -> Sales_No INT,
  -> Sales_Name VARCHAR(50),
  -> Branch VARCHAR(50),
  -> Sales_Amount DECIMAL(10, 2),
  -> DOB DATE
  -> );

### 2. Insert five records

- INSERT INTO Sales (Sales_No, Sales_Name, Branch, Sales_Amount, DOB)
  -> VALUES
  -> (1, 'John Doe', 'North', 15000.00, '1990-12-21'),
  -> (2, 'Jane Smith', 'South', 20000.00, '1985-06-15'),
  -> (3, 'Emily Davis', 'East', 18000.00, '1992-12-10'),
  -> (4, 'Michael Brown', 'West', 22000.00, '1988-03-05'),
  -> (5, 'Sarah Wilson', 'North', 17000.00, '1991-12-25');

### 3. Calculate total salesamount in each branch

- SELECT Branch, SUM(Sales_Amount) AS Total_Sales_Amount
  -> FROM Sales
  -> GROUP BY Branch;

### 4. Calculate average salesamount in each branch

- SELECT Branch, AVG(Sales_Amount) AS Average_Sales_Amount
  -> FROM Sales
  -> GROUP BY Branch;

### 5. Display all the salesmen, DOB who are born in the month of December as day in character format i.e. 21-Dec-09

- SELECT Sales_Name, DATE_FORMAT(DOB, '%d-%b-%y') AS DOB
  -> FROM Sales
  -> WHERE MONTH(DOB) = 12;

### 6. Display the name and DOB of salesman in alphabetical order of the month.

- SELECT Sales_Name, DOB
  -> FROM Sales
  -> ORDER BY DATE_FORMAT(DOB, '%M');
