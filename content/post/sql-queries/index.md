---
title: SQL Queries
subtitle: SQL Statements
date: 2024-02-18T17:15:54.173Z
summary: S﻿QL Statements
draft: false
featured: false
tags:
  - SQL
image:
  filename: sql-basics-cheat-sheet-a4-page-1.png
  focal_point: Smart
  preview_only: false
---
## *SQL Basics Cheat Sheet* 1

![## *SQL Basics Cheat Sheet*](sql-basics-cheat-sheet-a4-page-1.png "## *SQL Basics Cheat Sheet*")

## *SQL Basics Cheat Sheet*  2

![## *SQL Basics Cheat Sheet 2*](sql-basics-cheat-sheet-a4-page-2.png "## *SQL Basics Cheat Sheet 2*")

### Creating and managing databases

**Creates a new database.**

```sql
CREATE DATABASE bank;
```

**Delete/Drop a database and all of its contents**

```sql
DROP DATABASE bank;
```

**Show all databases in your cluster.**

```sql
SHOW DATABASES;
```



`IF EXISTS` can be used to prevent errors if we (for example) attempt to delete a database that doesn’t exist.

`IF EXISTS` can also be used with many other SQL statements and combined with other operators.

**Examples:**

| `DROP DATABASE IF EXISTS bank;` | `CREATE DATABASE IF NOT EXISTS bank;` |
| ------------------------------- | ------------------------------------- |

`DROP DATABASE … CASCADE` can be used to remove all objects that rely on the database that is being dropped. `DROP DATABASE … RESTRICT` can be used to prevent the `DROP DATABASE` command from executing unless the database is empty.

**Examples:**

| `DROP DATABASE bank CASCADE;` | `DROP DATABASE bank RESTRICT;` |
| ----------------------------- | ------------------------------ |



### Creating tables and schema

**Create a new table in the database.**

```sql
CREATE TABLE users (
        id UUID PRIMARY KEY,
        city STRING,
        name STRING,
        address STRING,
        credit_card STRING,
        dl STRING
);
```



#### Define a multi-column primary key:

```sql
CREATE TABLE users (
        id UUID,
        city STRING,
        name STRING,
        PRIMARY KEY (city, id)
);
```

#### Define a foreign key referencing another table in the database:

(In this case, referencing a column called `city` in table called `locations`).

```sql
CREATE TABLE users (
        id UUID PRIMARY KEY,
        city STRING REFERENCES locations(city),
        name STRING
);
```

#### Create an index based on a column:

```sql
CREATE TABLE users (
        id UUID PRIMARY KEY,
        city STRING,
        name STRING,
        INDEX (name)
);
```

#### Disallow `NULL` values from a column:

```sql
CREATE TABLE users (
        id UUID NOT NULL,
        city STRING,
        name STRING
);
```

#### Create a new table using the results of a query:

```sql
CREATE TABLE users_ny(user_id, name, city) 
AS SELECT * FROM users 
WHERE city = 'new york';
```

### Managing SQL tables

#### ALTER TABLE

Apply a schema change to a table.

```sql
ALTER TABLE bank ADD COLUMN active BOOL;

```

`ALTER TABLE` is used with subcommands such as:

#### ADD COLUMN

Add a column.

```sql
ALTER TABLE bank ADD COLUMN active BOOL;

```

#### DROP COLUMN

Remove a column.

```sql
ALTER TABLE bank DROP COLUMN active;

```

#### ALTER COLUMN

Change column constraints, datatypes, etc.

```sql
ALTER TABLE bank ALTER account_balance TYPE FLOAT;

```

#### RENAME COLUMN

Rename a column.

```sql
ALTER TABLE bank RENAME COLUMN account_balance TO balance;

```

#### RENAME TO

Rename a table.

```sql
ALTER TABLE bank RENAME TO users;

```

#### DROP TABLE

Remove a table.

```sql
DROP TABLE bank;

```

`DROP TABLE … CASCADE` can be used to remove all objects (constraints, views, etc.) that rely on the table being dropped.

`DROP TABLE … RESTRICT` can be used to prevent the DROP TABLE command from executing unless the table is empty.

Use `DROP TABLE` statements with caution!

### Inserting data

#### INSERT INTO … VALUES

Insert rows with specified values into a table.

```sql
INSERT INTO users (name, city) VALUES('Alice', 'New York');

```

#### INSERT INTO … SELECT

Insert rows into a table from the results of a query.

```sql
INSERT INTO drivers (id, city, name, address)
    SELECT id, city, name, address FROM users
    WHERE name IN ('Anita Atkinson', 'Devin Jordan');

```