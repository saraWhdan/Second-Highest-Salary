# LeetCode Problem: Second Highest Salary

## Problem Link
[Second Highest Salary - LeetCode](https://leetcode.com/problems/second-highest-salary/description/?envType=study-plan-v2&envId=top-sql-50)

## Problem Description

You are given a table `employee` with columns `id` and `salary`, where each row represents an employee. The `id` field is guaranteed to be unique for each employee.

Write an SQL query to find the second highest salary from the `employee` table.

| id | salary |
|----|--------|
| 1  | 100    |
| 2  | 200    |
| 3  | 300    |

For example, given the above `employee` table, the query should return `200` as the second highest salary. If there is no second highest salary, then the query should return `null`.


## Solution

```sql
SELECT MAX(salary) AS SecondHighestSalary
FROM employee
WHERE salary < (
    SELECT MAX(salary)
    FROM employee
);
