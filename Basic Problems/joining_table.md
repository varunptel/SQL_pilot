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


### Solution: Self-Join approach

By joining the table to itself, we can align each employee's salary directly with their manager's salary on the same row for comparison.

```sql
SELECT e.name AS Employee
FROM Employee e
INNER JOIN Employee m 
ON e.managerId = m.id
WHERE e.salary > m.salary;
```


---



### 3. INNER JOIN approach
You have a Users table and a Repositories table. You need to find which user owns which repository.

Goal: List the username and the repo_name for all repositories.

```sql
SELECT 
    Users.username, 
    Repositories.repo_name
FROM Users
INNER JOIN Repositories ON Users.user_id = Repositories.owner_id;
```

---


### 4. 
Scenario: In a PullRequests table, each PR has an author_id and a reviewer_id. Both IDs refer back to the same Employees table.

Goal: Generate a list showing the Pull Request ID, the name of the Author, and the name of the Reviewer.

```sql
SELECT 
    pr.pr_id,
    author.name AS author_name,
    reviewer.name AS reviewer_name
FROM PullRequests pr
JOIN Employees author ON pr.author_id = author.emp_id
JOIN Employees reviewer ON pr.reviewer_id = reviewer.emp_id;
```

---


