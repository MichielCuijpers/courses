## Course tasks
* Understand the notion of data layer
* Understand what an RDBMS is
* Understand concepts of table, column, row, field, data type
* Understand the role of SQL
* Install an RDBMS
* Create a simple database schema
* Execute a simple SQL query


## Introduction
* A business needs to organize its information
* Database solution
  * Οrganized collection of information
  * Set of tables each having different class of data


## Data layer
* The data layer is the behind-the-scenes structure
* Sites, applications and mobile apps tap into data layer for timely and consistent visitor data
![](media/dataLayer.png)


## Files vs. Relational Databases (1/2)
Issues when using file systems
* Data redundancy and inconsistency
  * Multiple file formats
  * Information repeated in multiple files
* Access to information
  * Each new function requires coding from scratch
* Data isolation
  * Cannot isolate information due to multiple files and formats


## Files vs. Relational Databases (2/2)
File systems issues when dealing with data storage
* Atomicity of updates
  * Data updates may be partially executed
  * Information repeated in multiple files
* Concurrent access (simultaneous access of multiple users)
  * Required for efficient systems
  * Multiple access may lead to inconsistencies
* Security issues
Relational Database Systems (RDBMS) deal with all the aforementioned


## What is an RDBMS
* RDBMS stands for Relational Database Management System. RDBMS is the basis for SQL, and for all modern database systems like MS SQL Server, IBM DB2, Oracle, MySQL, and Microsoft Access
* A Relational database management system (RDBMS) is a database management system (DBMS) that is based on the relational model as introduced by E. F. Codd
* Known Relation Database Management Systems
  * MySQL
  * Oracle
  * Microsoft SQL Server
  * PostgreSQL
  * IBM DB2


## What is a table
* The data in RDBMS is stored in database objects called tables
* A collection of related data entries and it consists of columns and rows
* The most common and simplest form of data storage in a relational database
* Following is the example of a CUSTOMERS table
![](media/table.png)


## What is a field
* Every table is broken up into smaller entities called fields
* The fields in the CUSTOMERS table consist of ID, NAME, AGE, ADDRESS and SALARY
* A field is a column in a table that is designed to maintain specific information about every record in the table
![](media/table.png)


## What is a record or row
* A record, is also called a row of data
* Is each individual entry that exists in a table
* There are 7 records in the following CUSTOMERS table
* A record is a horizontal entity in a table
![](media/table.png)


## What is a column
* A column is a vertical entity in a table that contains all information associated with a specific field in a table
* A column in the CUSTOMERS table is ADDRESS, which represents location description and would consist of the following
![](media/column.png)


## What is a primary key (1/2)
* Each database table must contain one or more columns that can be used to uniquely identify each row in the table. This is known in database terminology as the Primary Key
  * e.g. a table may use social security number column as the primary key
* Primary keys allow the database management system to uniquely identify a specific row in a table
* Without a primary key it would not be possible to retrieve or delete a specific row in a table because there can be no certainty that the correct row has been selected
  * Without a primary key it would not be possible to retrieve or delete a specific row in a table because there can be no certainty that the correct row has been selected


## What is a primary key (2/2)
* Without some guaranteed way to uniquely identify a specific row it would be impossible to ensure the correct data was being accessed at any given time
* Primary keys can comprise a single column or multiple columns in a table. To qualify as a single column primary key, no two rows can contain matching primary key values
* When using multiple columns to construct a primary key, individual column values do not need to be unique, but all the columns combined must be unique


## SQL General Data Types (1/3)
* Each column in a database table is required to have a name and a data type
* Decide what types of data will be stored inside each and every table column when creating a SQL table
* The data type is a label and a guideline for SQL to understand what type of data is expected inside of each column, and it also identifies how SQL will interact with the stored data


## SQL General Data Types (2/3)
* The following table lists the general data types in SQL

| Data type | Description |
| --- | --- |
| CHARACTER(n) | Character string. Fixed-length n |
| VARCHAR(n) | Character string. Variable length. Maximum length n |
| BOOLEAN | Stores TRUE or FALSE values |
| INTEGER(p) | Integer numerical (no decimal). Precision p |
| SMALLINT | Integer numerical (no decimal). Precision 5 |
| INTEGER | Integer numerical (no decimal). Precision 10 |


## SQL General Data Types (3/3)
| Data type | Description |
| --- | --- |
| BIGINT | Integer numerical (no decimal). Precision 19 |
| DECIMAL(p,s) | Exact numerical, precision p, scale s. Example: decimal(5,2) is a number that has 3 digits before the decimal and 2 digits after the decimal |
| NUMERIC(p,s) Exact numerical, precision p, scale s. (Same as DECIMAL) |
| FLOAT(p) |Approximate numerical, mantissa precision p. A floating number in base 10 exponential notation. The size argument for this type consists of a single number specifying the minimum precision |
| REAL | Approximate numerical, mantissa precision 7 |
| DOUBLE PRECISION | Approximate numerical, mantissa precision 16 |
| DATE | Stores year, month, and day values |
| TIME | Stores hour, minute, and second values |
| TIMESTAMP | Stores year, month, day, hour, minute, and second values |


## Examples - Character String: CHARACTER(8)
* Valid examples
  * ‘one’
  * ‘example’
  * ‘coding’
  * ‘04-10-16’
  * ‘bootcamp ’ (blank characters are truncated)

* Invalid examples
  * 12345
  * Bootcamps
  * 04-10-2016


## Examples - Character String: VARCHAR(10)
* Valid examples
  * ‘two’
  * ‘examples’
  * ‘coding’
  * ‘04-10-2016’
  * ‘bootcamp’

* Invalid examples
  * 12345
  * programming
  * 04-10-2016


## Examples - BOOLEAN
* Valid examples
  * true
  * True
  * TRUE
  * False
  * false

* Invalid examples
  * Yes
  * No
  * 0
  * 1


## Examples - INTEGER(7)
* Valid examples
  * 1234567
  * -1234567
  * 0
  * 12345
  * -12345

* Invalid examples
  * 12345678
  * -12345678
  * 123456789


## Examples - DECIMAL(10,3)
* Valid examples
  * 1234567
  * 1234567.123
  * 1234567.1234 (final digit is truncated)
  * -1234567
  * -1234567.123

* Invalid examples
  * 12345678
  * -12345678
  * -12345678.12
  * 123456789.123


## Examples - DATE
* Valid examples
  * 2016-10-06
  * 06-10-2016
  * 6-3-2016

* Invalid examples
  * 1024
  * date


## Examples - TIME
* Valid examples
  * 00:00:00
  * 13:30:00
  * 01:12:45.02
  * 23:59:59.99

* Invalid examples
  * 24:00:01.00
  * 11:15


## Examples - TIMESTAMP
* Valid examples
  * 2016-10-03 00:00:00.00
  * 2016-10-03 12:30:25.10
  * 2015-27-05 21:15:00.00

* Invalid examples
  * 2016-24-24 00:00:00.00
  * 2016-10-03 15:62:00.00
  * 2016-10-03 18:34:61.00


## Understanding the role of SQL
* Language to communicate with the database
* Retrieve the required information from a database
* Syntax of SQL is in plain English
* Used to question the database


## What SQL can do
* Execute queries against a database
* Perform CRUD function examples
  * Create (new databases, new tables in database, records in a database)
  * Read (retrieve data from a database)
  * Update (update records in a database)
  * Delete (delete records from a database)


## SQL Statements
Most of the actions needed to be performed on a database are done with SQL statements
* Most common SQL Commands
  * SELECT - extracts data from a database
  * UPDATE - updates data in a database
  * DELETE - deletes data from a database
  * INSERT INTO - inserts new data into a database
  * CREATE DATABASE - creates a new database
  * ALTER DATABASE - modifies a database
  * CREATE TABLE - creates a new table
  * ALTER TABLE - modifies a table
  * DROP TABLE - deletes a table


## SELECT Statement
* Is used to select data from a database
* The result is stored in a result table, called the result-set

SQL SELECT Syntax
```
SELECT column_name,column_name
FROM table_name;
```
or
```
SELECT * FROM table_name;
```

Example
```
SELECT * FROM Customers;
```


## SELECT DISTINCT Statement
* Is used to return only distinct (different) values
* In a table, a column may contain many duplicate values and sometimes you only want to list the different (distinct) values
* The DISTINCT keyword can be used to return only distinct (different) values

SQL SELECT Syntax
```
SELECT DISTINCT column_name,column_name
FROM table_name;
```

Example
```
SELECT DISTINCT City FROM Customers;
```


## WHERE Clause
* Is used to filter records

SQL SELECT Syntax
```
SELECT column_name,column_name
FROM table_name
WHERE column_name operator value;
```

Example
```
SELECT * FROM Customers WHERE Country='Mexico';
```


## AND & OR Operators
* The AND operator displays a record if both the first condition AND the second condition are true
* The OR operator displays a record if either the first condition OR the second condition is true

SQL AND Syntax
```
SELECT column_name,column_name
FROM table_name
WHERE condition1=true AND condition2=true;
```

Examples
```
Example SELECT * FROM Customers
WHERE City='Berlin'
OR City='München';
```
```
SELECT * FROM Customers
WHERE Country='Germany'
AND (City='Berlin' OR City='München');
```


## ORDER BY Keyword
* Is used to sort the result-set by one or more columns
* Sorts the records in ascending order by default. To sort the records in a descending order, you can use the DESC keyword

SQL ORDER BY Syntax
```
SELECT column_name, column_name
FROM table_name
ORDER BY column_name ASC|DESC, column_name ASC|DESC;
```

Examples
```
SELECT * 
FROM Customers 
ORDER BY Country;
```
```
SELECT * 
FROM Customers 
ORDER BY Country ASC, CustomerName DESC;
```


## The IN Operator
* The IN operator allows you to specify multiple values in a WHERE clause
```
SELECT column_name(s)
FROM table_name
WHERE column_name IN (value1,value2,...);
```
Examples
```
example ISELECT * FROM Customers
WHERE City IN ('Paris','London');
```
and
```
SELECT * FROM Customers
WHERE City IN (
Select cityname
From Cities
);
```


## INSERT INTO Statement
* Is used to insert new records in a table.

SQL INSERT INTO Syntax
* It is possible to write the INSERT INTO statement in two forms.
  * The first form does not specify the column names where the data will be inserted, only their values
```
INSERT INTO table_name
VALUES (value1,value2,value3,...);  
```
  * The second form specifies both the column names and the values to be inserted
```
INSERT INTO table_name (column1,column2,column3,...)
VALUES (value1,value2,value3,...);
```
Example
```
INSERT INTO Customers (CustomerName, ContactName, Address, City, Country)
VALUES ('Cardinal','Tom Erichsen','Skagen 21','Stavanger','Norway');
```


## UPDATE Statement
* Is used to update records in a table

SQL UPDATE INTO Syntax
```
UPDATE table_name
SET column1=value1,column2=value2,...
WHERE some_column=some_value;
```
Example
```
UPDATE Customers
SET ContactName='Alfred Schmidt', City='Hamburg'
WHERE CustomerName='Alfreds Futterkiste';
```


## DELETE Statement
* Is used to delete rows in a table

SQL DELETE INTO Syntax
```
DELETE FROM table_name
WHERE some_column=some_value;
```
Example
```
DELETE FROM Customers
WHERE CustomerName='Alfreds Futterkiste' AND ContactName='Maria Anders';
```


## SQL Functions
* SQL has many built-in functions for performing calculations on data
* SQL aggregate functions return a single value, calculated from values in a column

Useful aggregate functions:
* AVG() - Returns the average value
* COUNT() - Returns the number of rows
* FIRST() - Returns the first value
* LAST() - Returns the last value
* MAX() - Returns the largest value
* MIN() - Returns the smallest value
* SUM() - Returns the sum


## AVG() Function
* The AVG() function returns the average value of a numeric column

SQL AVG() Syntax
```
SELECT AVG(column_name) 
FROM table_name;
```

Example
```
SELECT AVG(Price) AS PriceAverage 
FROM Products;
```


## COUNT() Function (1/2)
* The COUNT() function returns the number of rows that matches a specified criteria
* The COUNT(column_name) function returns the number of values (NULL values will not be counted) of the specified column

SQL COUNT(column_name) Syntax
```
SELECT COUNT(column_name) 
FROM table_name;
```
Example
```
SELECT COUNT(CustomerID) AS OrdersFromCustomerID7 
FROM Orders 
WHERE CustomerID=7;
```


## COUNT() Function (1/2)
The COUNT(*) function returns the number of records in a table
SQL COUNT(*) Syntax
```
SELECT COUNT(*) 
FROM table_name;
```
Example
```
SELECT COUNT(*) AS NumberOfOrders 
FROM Orders;
```


## MAX() Function
* Returns the largest value of the selected column

SQL MAX() Syntax
```
SELECT MAX(column_name) 
FROM table_name;
```

Example
```
SELECT MAX(Price) AS HighestPrice 
FROM Products;
```


## MIN() Function
* Returns the smallest value of the selected column

SQL MIN() Syntax
```
SELECT MIN(column_name) 
FROM table_name;
```

Example
```
SELECT MIN(Price) AS SmallestOrderPrice  
FROM Products;
```


## SUM() Function
* Returns the total sum of a numeric column

SQL SUM() Syntax
```
SELECT SUM(column_name) 
FROM table_name;
```

Example
```
SELECT SUM(Quantity) AS TotalItemsOrdered 
FROM OrderDetails;
```


## GROUP BY Statement
* The GROUP BY statement is used in conjunction with the aggregate functions to group the result-set by one or more columns

SQL GROUP BY Syntax
```
SELECT column_name, aggregate_function(column_name)
FROM table_name
WHERE column_name operator value
GROUP BY column_name;
```

Example
```
SELECT ShipperName,COUNT(OrderID) AS NumberOfOrders FROM Orders
GROUP BY ShipperName;
```


## HAVING Clause
* The HAVING clause was added to SQL because the WHERE keyword could not be used with aggregate functions

SQL HAVING Syntax
```
SELECT column_name, aggregate_function(column_name)
FROM table_name
WHERE column_name operator value
GROUP BY column_name
HAVING aggregate_function(column_name) operator value;
```

Example
```
SELECT Employees.LastName, COUNT (OrderID) AS NumberOfOrders FROM Orders
GROUP BY LastName
HAVING COUNT(Orders.OrderID) > 10;
```


## Install MySQL RDBMS
* Download MySQL from http://dev.mysql.com/downloads/mysql/
![](media/mysql1.png)


## Install MySQL Workbench / MySQL Server
![](media/mysql2.png)


## Install MySQL Workbench / MySQL Server
![](media/mysql3.png)


## Install MySQL Workbench / MySQL Server
![](media/mysql4.png)


## Install MySQL Workbench / MySQL Server
![](media/mysql5.png)


## Install MySQL Workbench / MySQL Server
![](media/mysql6.png)


## Install MySQL Workbench / MySQL Server
![](media/mysql7.png)


## Install MySQL Workbench / MySQL Server
![](media/mysql8.png)


## Install MySQL Workbench / MySQL Server
![](media/mysql9.png)


## Install MySQL Workbench / MySQL Server
![](media/mysql10.png)


## Install MySQL Workbench / MySQL Server
![](media/mysql11.png)


## Install MySQL Workbench / MySQL Server
![](media/mysql12.png)


## Install MySQL Workbench / MySQL Server
![](media/mysql13.png)


## Install MySQL Workbench / MySQL Server
![](media/mysql14.png)


## Install MySQL Workbench / MySQL Server
![](media/mysql15.png)


## Install MySQL Workbench / MySQL Server
![](media/mysql16.png)


## Install MySQL Workbench / MySQL Server
![](media/mysql17.png)


## Install MySQL Workbench / MySQL Server
![](media/mysql18.png)


## Install MySQL Workbench / MySQL Server
![](media/mysql19.png)


## Install MySQL Workbench / MySQL Server
![](media/mysql20.png)


## Install MySQL Workbench / MySQL Server
![](media/mysql21.png)


## Install MySQL Workbench / MySQL Server
![](media/mysql22.png)


## Install MySQL Workbench / MySQL Server
![](media/mysql23.png)


## Install MySQL Workbench / MySQL Server
![](media/mysql24.png)


## Install MySQL Workbench / MySQL Server
![](media/mysql25.png)


## Install MySQL Workbench / MySQL Server
![](media/mysql26.png)


## Install MySQL Workbench / MySQL Server
![](media/mysql27.png)


## Install MySQL Workbench / MySQL Server
![](media/mysql28.png)


## Install MySQL Workbench / MySQL Server
![](media/mysql29.png)


## Create a new Database
![](media/createdb1.png)


## Create a new Database
![](media/createdb2.png)


## Create a new Database
![](media/createdb3.png)


## Create a new Database
![](media/createdb4.png)


## Create a new Database
![](media/createdb5.png)


## Create a new Database
![](media/createdb6.png)


## Exercise 1
* Create a new table named “Courses”, having as columns 
  * course id
  * name
  * name of the lecturer
  * name of the assistant
  * duration of the course (in days)
  * starting date of the course


## Exercise 2
* Select all values from table "Students", created earlier


## Exercise 3
* Insert into table "Students" three dummy values
* Then select the distinct values of this table


## Exercise 4
* Insert the following values into "Courses" table
| course_id | name | lecturer_name | assistant_name | duration | starting_date |
| --- | --- | --- | --- | --- | --- |
| 1 | SQL | AG | BN | 2 | 2016-10-21 |
| 2 | JAVA | VS | BN | 3 | 2016-10-25 |
| 3 | R | KP | TT | 4 | 2016-11-09 |
| 4 | PYTHON | KK | DD | 5 | 2016-11-09 |


## Exercise 5
* Display the number of the records contained in table "Students"


## Exercise 6
* Select the courses from table "Courses" that have duration more than 3 days


## Exercise 7
* Select students that are older than the age of 17


## Exercise 8
* Display only the month that "SQL" course will take place


## Exercise 9
* Select the details of the courses that have duration more than 2 days and start in November


## Exercise 10
* Calculate the total amount of teaching days per Lecturer
* and display the lecturers that have teaching experience more than 2 days


## Exercise 11
* Calculate the total amount of teaching days per Lecturer
* and display the lecturers that have teaching experience more than 2 days
