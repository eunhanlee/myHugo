---
title : "Second Highest Salary"
date : "2021-05-12"
tags : [algorithm problem solving, Second Highest Salary]
topics : [ProblemSolving]
---

## Problem

[Problem_Link](https://leetcode.com/problems/second-highest-salary/)

- 1 hour limit
- no search on internet


Write a SQL query to get the second highest salary from the Employee table.

| Id  | Salary |
| --- | ------ |
| 1   | 100    |
| 2   | 200    |
| 3   | 300    |

For example, given the above Employee table, the query should return 200 as the second highest salary. If there is no second highest salary, then the query should return null.

| SecondHighestSalary |
| ------------------- |
| 200                 |

## My Answer

### Overview

### My code

MYSQL from internet search

```sql
SELECT
    (SELECT DISTINCT Salary#select column named "salary"
        FROM Employee #from table named "Empolyee"
        ORDER BY Salary DESC #sorting 내림차순 Descending and AESC오름차순
     LIMIT 1 #only pick one
     OFFSET 1 #move second one. if its 3, it will pick 4th data.
    ) AS SecondHighestSalary #put data into SecondHighestSalary
```

basically, sort in Descending and pick second data.

> "if there is no such second highest salary since there might be only one record in this table. To overcome this issue, we can take this as a temp table."

## Reflect on

- I have used SQL before. However, I got data from there and took care of it with JAVA. Thus, it took a lot of time to solve this problem.

## Other Answers

- Simple query which handles the NULL situation

  ```java
  SELECT max(Salary) AS SecondHighestSalary
  FROM Employee
  WHERE Salary < (SELECT max(Salary) FROM Employee)
  ```

- Using sub-query and LIMIT clause [Accepted]

  ```sql
  SELECT
      (SELECT DISTINCT
              Salary
          FROM
              Employee
          ORDER BY Salary DESC
          LIMIT 1 OFFSET 1) AS SecondHighestSalary
  ;
  ```

- Using IFNULL and LIMIT clause [Accepted]

  ```sql
  SELECT
      IFNULL(
        (SELECT DISTINCT Salary
         FROM Employee
         ORDER BY Salary DESC
          LIMIT 1 OFFSET 1),
      NULL) AS SecondHighestSalary
  ```

## Additional Study needed
