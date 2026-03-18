# Basic SQL Practice Problems

This section contains foundational SQL problems designed to practice filtering, joining, and basic aggregations.

## Table creation:

```sql
-- Create Tables:
CREATE TABLE customers (
    customer_id INT PRIMARY KEY,
    customer_name VARCHAR(100),
    city VARCHAR(50),
    loyalty_score INT
);

CREATE TABLE orders (
    order_id INT PRIMARY KEY,
    customer_id INT,
    order_date DATE,
    total_amount DECIMAL(10,2)
);

CREATE TABLE departments (
    dept_id INT PRIMARY KEY,
    dept_name VARCHAR(50)
);

CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    name VARCHAR(100),
    dept_id INT,
    salary INT
);

-- Insert data into customers table:
INSERT INTO customers VALUES
(1, 'Alice Johnson', 'New York', 85),
(2, 'Bob Smith', 'Los Angeles', 40),
(3, 'Charlie Brown', 'New York', 92);

-- Insert data into orders table:
INSERT INTO orders VALUES
(101, 1, '2024-01-10', 150.00),
(102, 1, '2024-02-15', 200.00),
(103, 2, '2024-03-01', 50.00);

-- Insert data into departments table
INSERT INTO departments VALUES
(1, 'Engineering'),
(2, 'Marketing'),
(3, 'Sales');


-- Insert data into employees table
INSERT INTO employees VALUES
(1, 'John', 1, 90000),
(2, 'Sarah', 1, 95000),
(3, 'Mike', 2, 80000);
```


## PROBLEMS AND SOLUTIONS: 

1. High-Value Customers
Goal: Find all customers in 'New York' with a loyalty score above 80.

```sql
SELECT customer_id, customer_name FROM customers
WHERE city = 'New York' AND loyalty_score > 80;
```

2. Customer Order History
Goal: Generate a list of all orders including the customer's name and the date they placed the order.
```sql
SELECT 
    o.order_id, 
    c.customer_name, 
    o.order_date
FROM orders o
JOIN customers c ON o.customer_id = c.customer_id;
```
3. Departmental Headcount
Goal: Count how many employees are in each department. Only show departments that have at least one employee.

```sql
SELECT 
    d.dept_name, 
    COUNT(e.employee_id) AS total_employees
FROM departments d
JOIN employees e ON d.dept_id = e.dept_id
GROUP BY d.dept_name;
```
4. Product_id counts
Table: Products

+-------------+---------+
| Column Name | Type    |
+-------------+---------+
| product_id  | int     |
| low_fats    | enum    |
| recyclable  | enum    |
+-------------+---------+
product_id is the primary key (column with unique values) for this table.
low_fats is an ENUM (category) of type ('Y', 'N') where 'Y' means this product is low fat and 'N' means it is not.
recyclable is an ENUM (category) of types ('Y', 'N') where 'Y' means this product is recyclable and 'N' means it is not.
 

Write a solution to find the ids of products that are both low fat and recyclable.

Return the result table in any order.

The result format is in the following example.

 

Example 1:

Input: 
Products table:
+-------------+----------+------------+
| product_id  | low_fats | recyclable |
+-------------+----------+------------+
| 0           | Y        | N          |
| 1           | Y        | Y          |
| 2           | N        | Y          |
| 3           | Y        | Y          |
| 4           | N        | N          |
+-------------+----------+------------+
Output: 
+-------------+
| product_id  |
+-------------+
| 1           |
| 3           |
+-------------+
Explanation: Only products 1 and 3 are both low fat and recyclable.

```sql
SELECT product_id FROM Products
WHERE low_fats = 'Y'
AND recyclable = 'Y';
```


