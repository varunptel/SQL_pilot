# SQL: Structured Query Language

**SQL** (originally Structured English Query Language) is the standard language used to manage and manipulate **Relational Databases**. It allows developers to interact with database software to store, retrieve, and edit data efficiently.

---

## Database Types
Broadly speaking, there are two main types of databases:
1.  **SQL (Relational Databases):** Data is stored in structured tables with rows and columns.
2.  **NoSQL (Non-Relational Databases):** Data is stored in documents, graphs, or key-value pairs.

---

## Joining Tables
One of the most powerful features of SQL is the ability to join multiple rows from two or more tables based on a correlated column between them.

### 1. INNER JOIN
The `INNER JOIN` keyword selects records that have matching values in both tables. If a row in one table doesn't have a match in the other, it won't appear in the results.



#### **Syntax:**
```sql
SELECT column_name(s)
FROM (table1
INNER JOIN table2
ON table1.column_name = table2.column_name);
```
(The bracket indicates that it returns new table and we can use this to join more tables the same way)



### 2. LEFT OUTER JOIN
The `LEFT JOIN` selects all the records from the left table and only matched record from the right table.

#### **Syntax:**
```sql
SELECT column_name(s)
FROM table1
LEFT JOIN table2
ON table1.column_name = table2.column_name;
```

If there is no match from the right table then the result for the column from the right table is NULL.
