````md
# SQL + DBMS Placement Preparation

## 1. SQL Basics — Revision

### 1.1 What is SQL?

SQL (Structured Query Language) is used to communicate with and manage relational databases.

### 1.2 Database / Table / Row / Column

- **Database** → Collection of related tables
- **Table** → Stores data in rows and columns
- **Row** → One complete record
- **Column** → Attribute/property of the data

### 1.3 SQL Command Categories

| Category | Full Form | Purpose | Commands |
|---|---|---|---|
| DDL | Data Definition Language | Defines/modifies structure | CREATE, ALTER, DROP, TRUNCATE |
| DML | Data Manipulation Language | Modifies data | INSERT, UPDATE, DELETE |
| DQL | Data Query Language | Retrieves data | SELECT |
| DCL | Data Control Language | Controls permissions | GRANT, REVOKE |
| TCL | Transaction Control Language | Controls transactions | COMMIT, ROLLBACK, SAVEPOINT |

---

### 1.4 DDL Commands

#### CREATE
Creates a database object such as a table.

```sql
CREATE TABLE table_name (
    column1 datatype,
    column2 datatype
);
````

#### ALTER

Modifies the structure of an existing table.

```sql
ALTER TABLE table_name
ADD column_name datatype;
```

```sql
ALTER TABLE table_name
MODIFY column_name datatype;
```

```sql
ALTER TABLE table_name
DROP COLUMN column_name;
```

#### DROP

Removes the table and its structure.

```sql
DROP TABLE table_name;
```

#### TRUNCATE

Removes all rows while keeping the table structure.

```sql
TRUNCATE TABLE table_name;
```

**DROP vs TRUNCATE**

* DROP → removes table + structure
* TRUNCATE → removes rows, keeps structure

---

### 1.5 DML Commands

#### INSERT

Adds new rows.

```sql
INSERT INTO table_name (column1, column2)
VALUES (value1, value2);
```

#### UPDATE

Modifies existing rows.

```sql
UPDATE table_name
SET column1 = value1
WHERE condition;
```

#### DELETE

Removes rows.

```sql
DELETE FROM table_name
WHERE condition;
```

**Important:** Without `WHERE`, `UPDATE` or `DELETE` can affect all rows.

---

### 1.6 DQL — SELECT

Used to retrieve data from a table.

```sql
SELECT column1, column2
FROM table_name;
```

To retrieve all columns:

```sql
SELECT *
FROM table_name;
```

---

### 1.7 Primary Key

A Primary Key uniquely identifies each row in a table.

**Properties:**

* Must be unique
* Cannot be `NULL`
* A table can have only one Primary Key
* Primary Key can contain multiple columns (Composite Primary Key)

#### Syntax

Single-column Primary Key:

```sql
CREATE TABLE table_name (
    column_name datatype PRIMARY KEY
);
```

Table-level syntax:

```sql
PRIMARY KEY (column_name)
```

Composite Primary Key:

```sql
PRIMARY KEY (column1, column2)
```

---

### 1.8 Foreign Key

A Foreign Key creates a relationship between tables by referencing a key in another table.

**Properties:**

* References a Primary Key or suitable `UNIQUE` key
* Does not have to be unique
* Can contain `NULL` unless restricted
* Column names do not have to be the same
* Referencing and referenced data types should be compatible

#### Syntax

```sql
FOREIGN KEY (column_name)
REFERENCES referenced_table(referenced_column);
```

---

### 1.9 Basic Data Types

| Data Type      | Purpose               |
| -------------- | --------------------- |
| `INT`          | Whole numbers         |
| `DECIMAL(p,s)` | Exact decimal numbers |
| `VARCHAR(n)`   | Variable-length text  |
| `CHAR(n)`      | Fixed-length text     |
| `DATE`         | Date values           |
| `BOOLEAN`      | True/False values     |

**VARCHAR(n)** → Maximum `n` characters

**DECIMAL(p,s)** → `p` total digits, `s` digits after the decimal point

---

### Common Mistakes

* `DELETE` removes rows; `DROP` removes the table.
* `TRUNCATE` removes rows but keeps the table structure.
* `UPDATE` / `DELETE` without `WHERE` can affect every row.
* Primary Key → unique + cannot be `NULL`.
* Foreign Key → establishes a relationship; it does not have to be unique.
* Foreign Key column names do not need to match.
* `VARCHAR` and `CHAR` are not the same.


## 2. WHERE / AND / OR / NULL

### 2.1 WHERE

Filters rows based on a condition.

**Syntax**
```sql
SELECT column1, column2
FROM table_name
WHERE condition;
2.2 AND

Returns rows only when all conditions are true.

Syntax

SELECT *
FROM table_name
WHERE condition1
AND condition2;
2.3 OR

Returns rows when at least one condition is true.

Syntax

SELECT *
FROM table_name
WHERE condition1
OR condition2;
2.4 AND + OR

AND has higher precedence than OR.

Use parentheses when specific grouping is required.

Syntax

SELECT *
FROM table_name
WHERE condition1
AND (condition2 OR condition3);
2.5 NULL

NULL represents a missing or unknown value.

NULL is not 0 or an empty string.

Syntax

SELECT *
FROM table_name
WHERE column_name IS NULL;
SELECT *
FROM table_name
WHERE column_name IS NOT NULL;
2.6 Comparison Operators
Operator	Meaning
=	Equal
<>	Not equal
>	Greater than
<	Less than
>=	Greater than or equal
<=	Less than or equal
Common Mistakes
Use IS NULL, not = NULL.
AND has higher precedence than OR.
Use parentheses when specific logical grouping is required.
3. DISTINCT / ORDER BY
3.1 DISTINCT

Removes duplicate rows from the result.

For multiple columns, uniqueness is checked based on the combination of selected columns.

Syntax

SELECT DISTINCT column_name
FROM table_name;
SELECT DISTINCT column1, column2
FROM table_name;
3.2 ORDER BY

Sorts the result based on one or more columns.

Syntax

SELECT column1, column2
FROM table_name
ORDER BY column1 ASC;
SELECT column1, column2
FROM table_name
ORDER BY column1 DESC;

Multiple columns:

SELECT column1, column2
FROM table_name
ORDER BY column1 ASC, column2 DESC;
ASC → Ascending
DESC → Descending
ASC is the default.
Common Mistakes
DISTINCT applies to the combination of selected columns.
In multiple-column sorting, the first column has higher priority.
ORDER BY sorts the result; it does not modify stored data.
4. INSERT / UPDATE / DELETE
4.1 INSERT

Adds new rows to a table.

Syntax

INSERT INTO table_name (column1, column2, column3)
VALUES (value1, value2, value3);

Without specifying column names:

INSERT INTO table_name
VALUES (value1, value2, value3);
4.2 UPDATE

Modifies existing rows.

Syntax

UPDATE table_name
SET column1 = value1
WHERE condition;

Multiple columns:

UPDATE table_name
SET column1 = value1,
    column2 = value2
WHERE condition;
4.3 DELETE

Removes rows from a table.

Syntax

DELETE FROM table_name
WHERE condition;

To remove all rows:

DELETE FROM table_name;
Common Mistakes
UPDATE / DELETE without WHERE can affect all rows.
INSERT adds rows; UPDATE modifies existing rows.
DELETE removes rows, not the table.
When column names are omitted in INSERT, values must follow the table's column order.
---

```
```
