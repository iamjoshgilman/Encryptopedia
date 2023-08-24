---
creation date: May 21st 2023
last modified date: May 21st 2023
aliases: []
tags: #📖
---

Primary Categories: [[01 - Languages]] 
Secondary Categories: [[000 - Global Index]] 
Links: [[]] 
Search Tag: #📖  

# [[03 - SQL Cheatsheet]]  
---
# MySQL Cheatsheet

## Log into MySQL
```sql
mysql -h URL/IP -u username -p
```
Replace `username` with your MySQL username, then enter your password when prompted.

## Select a Database
```sql
USE database_name;
```
Replace `database_name` with the name of your database.

## List All Databases
```sql
SHOW DATABASES;
```
This command displays all databases in your MySQL server.

## List All Tables in the Current Database
```sql
SHOW TABLES;
```
This command displays all tables in the currently selected database.

## Show the Structure of a Table
```sql
DESCRIBE table_name;
```
Replace `table_name` with the name of your table. This command displays the structure of the specified table.

## Select All Data from a Table
```sql
SELECT * FROM table_name;
```
Replace `table_name` with the name of your table. This command displays all records from the specified table.

---

```SQL
-- Commenting in SQL
-- Single line comment

/*
Multi-line comment
*/

-- SELECTing data
SELECT * FROM your_table; -- selects all fields from the table
SELECT column1, column2 FROM your_table; -- select specific fields

-- WHERE clause (filtering)
SELECT * FROM your_table WHERE column1 = 'value'; -- equals
SELECT * FROM your_table WHERE column1 <> 'value'; -- not equals
SELECT * FROM your_table WHERE column1 > 'value'; -- greater than
SELECT * FROM your_table WHERE column1 < 'value'; -- less than

-- JOINing tables
-- Inner Join
SELECT column_name(s)
FROM table1
INNER JOIN table2
ON table1.column_name = table2.column_name;

-- Left Join
SELECT column_name(s)
FROM table1
LEFT JOIN table2
ON table1.column_name = table2.column_name;

-- Right Join
SELECT column_name(s)
FROM table1
RIGHT JOIN table2
ON table1.column_name = table2.column_name;

-- Full Outer Join
SELECT column_name(s)
FROM table1
FULL OUTER JOIN table2
ON table1.column_name = table2.column_name;

-- UNION operator (combining result sets)
SELECT column_name(s) FROM table1
UNION
SELECT column_name(s) FROM table2;

-- INSERTing data
INSERT INTO your_table (column1, column2) VALUES ('value1', 'value2');

-- UPDATEing data
UPDATE your_table SET column1 = 'new_value' WHERE column2 = 'value';

-- DELETEing data
DELETE FROM your_table WHERE column1 = 'value';

-- Creating and dropping tables
CREATE TABLE your_table (column1 datatype, column2 datatype);
DROP TABLE your_table;

-- Aggregation functions
SELECT COUNT(column1) FROM your_table; -- count of values
SELECT AVG(column1) FROM your_table; -- average of values
SELECT SUM(column1) FROM your_table; -- sum of values
SELECT MIN(column1) FROM your_table; -- minimum value
SELECT MAX(column1) FROM your_table; -- maximum value

-- GROUP BY and HAVING clauses
SELECT COUNT(column1), column2 FROM your_table GROUP BY column2; -- group by
SELECT COUNT(column1), column2 FROM your_table GROUP BY column2 HAVING COUNT(column1) > value; -- having

-- Subqueries
SELECT column1 FROM your_table WHERE column1 = (SELECT column1 FROM your_table WHERE column2 = 'value');

-- Show all tables in a database
SELECT * FROM INFORMATION_SCHEMA.TABLES WHERE TABLE_SCHEMA = 'your_database';

-- Show all columns of a table
SELECT COLUMN_NAME FROM INFORMATION_SCHEMA.COLUMNS WHERE TABLE_NAME = 'your_table';

-- Transactions
START TRANSACTION; -- or BEGIN WORK;
-- SQL operations
COMMIT; -- applies changes
ROLLBACK; -- rollbacks changes, cancelling the transaction

-- User management (note: these require superuser permissions)
CREATE USER 'username'@'localhost' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON database.table TO 'username'@'localhost';
FLUSH PRIVILEGES;
DROP USER 'username'@'localhost';
```


___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: May 21st 2023 (09:10 pm) 
Last Modified Date: May 21st 2023 (09:10 pm)
