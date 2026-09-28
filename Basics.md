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

---

```
```
