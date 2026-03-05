### SQL CREATE DATABASE
The CREATE DATABASE statement is used to create a new SQL database.

```sql
CREATE DATABASE databasename;
```
Make sure you have admin privilege before creating any database as most SQL accounts are restricted for basic tasks.

 ### The SQL DROP DATABASE
The DROP DATABASE statement is used to drop an existing SQL database.
```sql
DROP DATABASE databasename;
```
Be careful with dropping the database since it will delete the database and all its content permanently.

###SQL CREATE TABLE

```sql
CREATE TABLE table_name (
    column1 datatype constraint,
    column2 datatype constraint,
    column3 datatype constraint,
   ....
);
```

#### Create Table Using Another Table
Copy of an existing table can also be created with the help of CREATE TABLE. The new table gets the same column definitions. All columns or specific columns can be selected. If you create a new table using an existing table, the new table will be filled with the existing values from the old table.
```sql
CREATE TABLE new_table_name AS
    SELECT column1, column2,...
    FROM existing_table_name
    WHERE ....;
```

### ALTER TABLE 
`ALTER TABLE` is used to add, delete or modify the columns in an existing table. ALso, it can be used to add or drop different constraints on table.

***SYNTAX FOR ADD COLUMN***
 ```sql
ALTER TABLE table_name
ADD column_name datatype;
```

***SYNTAX FOR DROP COLUMN***

 ```sql
ALTER TABLE table_name
DROP COLUMN column_name;
```
***SYNTAX FOR RENAME COLUMN NAME***


```sql
ALTER TABLE table_name
RENAME COLUMN old_name to new_name;
```
(SYNTAX may change depending on the type of SQL Server one is using).

***ALTER/MODIFY DATATYPE***

```sql
ALTER TABLE table_name
ALTER COLUMN column_name new_datatype;
```
(SYNTAX may change depending on the type of SQL Server one is using).
```sql
ALTER TABLE table_name
MODIFY column_name new_datatype;
```

## SQL CONSTRAINTS:

They are used to specify the rules for data in the table.


The following constraints are commonly used in SQL:

| Constraint | Description |
| :--- | :--- |
| **NOT NULL** | Column cannot have a NULL value |
| **UNIQUE** | All values in a column are different |
| **PRIMARY KEY** | A combination of NOT NULL and UNIQUE; uniquely identifies each row |
| **FOREIGN KEY** | Prevents actions that would destroy links between tables |
| **CHECK** | Ensures values in a column satisfy a specific condition |
| **DEFAULT** | Sets a default value if no value is specified |
| **CREATE INDEX** | Used to create and retrieve data very quickly |


**W3Schools**: Referenced for SQL syntax and keyword definitions. [Link](https://www.w3schools.com/sql/)
