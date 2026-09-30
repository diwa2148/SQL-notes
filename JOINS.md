# SQL + DBMS Placement Preparation

## 5. INNER JOIN

Returns only matching rows from both tables.

### Syntax

```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;

JOIN = INNER JOIN

Common Mistakes
Wrong columns in ON
Ambiguous column names
6. LEFT JOIN / RIGHT JOIN
LEFT JOIN

Returns all rows from the left table and matching rows from the right table.

Syntax
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
RIGHT JOIN

Returns all rows from the right table and matching rows from the left table.

Syntax
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
Find Unmatched Rows
SELECT columns
FROM tableA a
LEFT JOIN tableB b
ON a.column = b.column
WHERE b.column IS NULL;
Common Mistakes
Confusing left/right table
Forgetting IS NULL for unmatched rows
7. SELF JOIN

Joins a table with itself.

Used when rows in the same table have relationships with other rows.

Syntax
SELECT columns
FROM table_name e
JOIN table_name m
ON e.column = m.column;
Employee-Manager
SELECT e.name AS employee,
       m.name AS manager
FROM employees e
JOIN employees m
ON e.manager_id = m.id;
e → employee
m → manager
ON → establishes the relationship
WHERE → filters the result
Common Mistakes
Confusing e.id and e.manager_id
Using the wrong alias
