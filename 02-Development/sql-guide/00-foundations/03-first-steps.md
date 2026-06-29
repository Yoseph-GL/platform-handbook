# SQL Foundations: First Steps

## Architecture / Rationale

Before you can write complex queries, you need to create a database and put data into it. These are the first practical steps after installation.

Key concepts:
- **Database**: a container that holds tables, views, and other objects.
- **Table**: a grid of rows and columns that stores data about one kind of thing (customers, products, orders).
- **Field / Column**: one piece of information in a table (a name, a price, a date).
- **Record / Row**: one complete entry in a table (one customer, one product).

## Query / Code Blocks

```sql
-- Create a new database
CREATE DATABASE IF NOT EXISTS app_db;
USE app_db;
```

```sql
-- Create a table with columns and a primary key
CREATE TABLE IF NOT EXISTS users (
  user_id INT AUTO_INCREMENT PRIMARY KEY,
  name VARCHAR(100) NOT NULL,
  last_name VARCHAR(150) NOT NULL,
  email VARCHAR(255) NULL,
  age INT NULL,
  created_at DATETIME NOT NULL DEFAULT CURRENT_TIMESTAMP
);
```

```sql
-- Your first SELECT query: read all rows from a table
SELECT *
FROM products;

-- Select specific columns
SELECT productname, price
FROM products;

-- Your first INSERT: add a new row
INSERT INTO users (name, last_name, age, email)
VALUES ('Maria', 'Lopez', 21, 'maria@example.com');
```

## Performance / Optimization Notes

- Start with one database per project. Do not mix unrelated tables in the same database.
- Choose column data types carefully. Use `INT` for numbers you calculate, `VARCHAR(n)` for short text, and `TEXT` for long text.
- Always create a primary key for every table. Auto-incrementing integers are a safe default.
- Test your first queries with `SELECT` before running `INSERT`, `UPDATE`, or `DELETE`.

[[01-what-is-sql]]
[[02-er-model]]
[[01-schema-foundations]]
[[04-safe-mutations]]
