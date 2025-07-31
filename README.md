# SQL-Refresher
SQL Refresher using PostgreSQL
- How to remove duplicates? Either through `DISTINCT` or `GROUP BY`. Using both at the same time is not necessary. In fact, if have `GROUP BY`, `DISTINCT` does nothing.
- What are the types of the joins we have? And when to use them?
<img width="600" height="472" alt="image" src="https://github.com/user-attachments/assets/f0ba10e8-a930-4af2-9a59-971ffda035dd" />
<img width="981" height="464" alt="Screenshot 2025-07-30 at 12 40 17" src="https://github.com/user-attachments/assets/9b478a31-9f64-4d90-8209-819c9fa956af" />
Table A: Employee
|emp_id|
---------
|1|
|2|
|3|
|4|

Table B: Salary
|emp_id| emp_sal|
---------
|1| 3000
|3| 6000

select a.emp_id, b.emp_sal from a left join b on a.emp_id = b.emp_id where b.emp_id is null

- How to use LEFT JOIN and WHERE safely?
- When to use IN and when to use EXISTS? How about LIKE? Is there a NOT LIKE?
- UNION ALL vs UNION:
- | Clause      | Combines Rows | Removes Duplicates   | Requires Column Match |
| ----------- | ------------- | -------------------- | --------------------- |
| `UNION`     | ✅             | ✅                    | ✅ Yes                 |
| `UNION ALL` | ✅             | ❌ (keeps duplicates) | ✅ Yes                 |

- Review Window Function
- Review INDEX
- Optimization techniques

### 🔍 Additional Advanced SQL Concepts to Review

1. **Set Operations**

   * `UNION`, `INTERSECT`, `EXCEPT`
   * Use cases: deduplication, mutual inclusion/exclusion logic

2. **Aggregation with `GROUP BY` & `HAVING`**

   * Nested aggregation
   * Filtering post-aggregation using `HAVING`

3. **Subqueries**

   * Correlated vs uncorrelated subqueries
   * `EXISTS`, `IN`, `NOT IN`, `ALL`, `ANY`

4. **Advanced Window Functions**

   * `LEAD`, `LAG`, `NTILE`, `RANK`, `DENSE_RANK`, `ROW_NUMBER`
   * Frame specifications: `ROWS BETWEEN`, `RANGE BETWEEN`

5. **Pivoting/Unpivoting**

   * CASE-based pivot logic
   * `PIVOT`, `UNPIVOT` (if your SQL dialect supports it)

6. **Recursive CTEs**

   * Tree/graph traversal
   * Hierarchical queries (e.g., org charts, file systems)

7. **Date & Time Manipulation**

   * `DATE_DIFF`, `DATE_ADD`, `EXTRACT`, formatting
   * Use in time-based windows or rollups

8. **Conditional Logic**

   * `CASE WHEN`, especially nested
   * Useful for encoding business rules

9. **Query Optimization & Performance**

   * Indexing awareness
   * Explain plans, avoiding cross joins, filtering early

10. **Data Cleaning & Transformation**

* NULL handling (`COALESCE`, `NULLIF`)
* String ops: `LIKE`, `REGEXP`, `TRIM`, `SPLIT`, etc.


### 🔥 Hard SQL Questions (LeetCode & HackerRank)

#### 📘 LeetCode (Hard-Level)

1. **[The Number of Employees Which Report to Each Employee](https://leetcode.com/problems/the-number-of-employees-which-report-to-each-employee/)**

   * CTEs, recursive joins

2. **[Monthly Transactions I & II](https://leetcode.com/problems/monthly-transactions-i/)**

   * Date functions, grouping, conditional aggregation

3. **[Employee Bonus](https://leetcode.com/problems/employee-bonus/)**

   * Joins + handling NULLs

4. **[Department Highest Salary](https://leetcode.com/problems/department-highest-salary/)**

   * Window function: `RANK()` or CTE + `MAX`

5. **[Sales Analysis III](https://leetcode.com/problems/sales-analysis-iii/)**

   * Subqueries with `NOT EXISTS`

6. **[Consecutive Available Seats](https://leetcode.com/problems/consecutive-available-seats/)**

   * Window function: `LEAD`, `LAG`, pattern recognition

7. **[Users Active Minutes (UAM)](https://leetcode.com/problems/users-active-minutes/)**

   * Aggregation + group count frequency

#### 🧠 HackerRank (Advanced Challenges)

1. **[Weather Observation Station 20](https://www.hackerrank.com/challenges/weather-observation-station-20/problem)**

   * Median logic with window functions

2. **[The Report](https://www.hackerrank.com/challenges/the-report/problem)**

   * Windowing, dense ranking

3. **[Challenges](https://www.hackerrank.com/challenges/challenges/problem)**

   * Joins across multiple tables, filters

4. **[Interviews](https://www.hackerrank.com/challenges/interviews/problem)**

   * CTEs + aggregation logic

5. **[New Companies](https://www.hackerrank.com/challenges/the-company/problem)**

   * Advanced join filters and exclusion logic
