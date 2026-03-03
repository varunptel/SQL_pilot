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

