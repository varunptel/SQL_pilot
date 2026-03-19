## 1. Combine Two Tables

### Problem Description
Write a solution to report the first name, last name, city, and state of each person in the **Person** table. If the address of a `personId` is not present in the **Address** table, report `null` instead.

**Tables:**

| Person Table | Type |
| :--- | :--- |
| personId | int (PK) |
| lastName | varchar |
| firstName | varchar |

| Address Table | Type |
| :--- | :--- |
| addressId | int (PK) |
| personId | int |
| city | varchar |
| state | varchar |

---

### Solution

To ensure we include everyone from the `Person` table even if they don't have a matching record in the `Address` table, we use a **LEFT JOIN**.

```sql
SELECT 
p.firstName,p.lastName, a.city, a.state
FROM Person p
LEFT JOIN Address a 
ON p.personId = a.personId;
```

## 2. Employees Earning More Than Their Managers

### Problem Description
Find all employees who earn more than their managers. Each row contains an `id`, `name`, `salary`, and `managerId`.

**Table: Employee**

| Column Name | Type    |
| :---        | :---    |
| id          | int     |
| name        | varchar |
| salary      | int     |
| managerId   | int     |

---

### Solution: Self-Join approach

By joining the table to itself, we can align each employee's salary directly with their manager's salary on the same row for comparison.

```sql
SELECT e.name AS Employee
FROM Employee e
INNER JOIN Employee m 
ON e.managerId = m.id
WHERE e.salary > m.salary;
```
