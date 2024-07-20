# Assignment 2: Client Master Table Operations

## Exercise: Update Records in the Client Master Table

### Task Overview

This assignment involves creating a `Client_Master` table, inserting records, performing updates, and executing SQL queries to retrieve and manipulate data.

### Questions and Commands

### 1.	create a client master table with attributes
-  CREATE TABLE Client_Master (
    ->        ClientNO VARCHAR(10),
    ->        Name VARCHAR(50),
    ->        Address VARCHAR(100),
    ->        City VARCHAR(50),
    ->        State VARCHAR(50),
    ->        bal_due DECIMAL(10, 2)
    ->    );

### 2.	insert five records into the Client_Master
- INSERT INTO Client_Master (ClientNO, Name, Address, City, State, bal_due)
    -> VALUES
    -> ('C101', 'Alice Johnson', '123 Maple St', 'Springfield', 'IL', 4500.00),
    -> ('C102', 'Bob Smith', '456 Oak St', 'Lincoln', 'NE', 5200.00),
    -> ('C103', 'Charlie Brown', '789 Pine St', 'Madison', 'WI', 3000.00),
    -> ('C104', 'Diana Prince', '101 Birch St', 'Salem', 'OR', 6500.00),
    -> ('C123', 'Eve Adams', '202 Cedar St', 'Reno', 'NV', 4800.00);

### 3.	Display Client Master Table
- SELECT * FROM Client_Master;

### 4.	Find the name of Clients whose balance_due >5000
- SELECT Name FROM Client_Master WHERE bal_due > 5000;

### 5.	Change the bal_due of ClientNO “C123” to Rs. 5100
- UPDATE Client_Master SET bal_due = 5100.00 WHERE ClientNO = 'C123';

### 6.	Change the name of Client_master to Client12
- RENAME TABLE Client_Master TO Client12;

### 7.	Display the bal_due heading as “BALANCE” Client master table
- SELECT ClientNO, Name, Address, City, State, bal_due AS BALANCE FROM Client12;
