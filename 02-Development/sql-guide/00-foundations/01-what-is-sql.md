# SQL Foundations: What is SQL

## Architecture / Rationale

SQL stands for Structured Query Language. It is the standard language for talking to relational databases. Every major database system speaks SQL.

Key facts:
- SQL is a declarative language. You describe *what* you want, not *how* to get it.
- SQL works with relational databases. These databases store data in tables with rows and columns.
- SQL is not a programming language like Python or Java. It has no loops or variables in its basic form (extensions like PL/pgSQL add them).

## Query / Code Blocks

```sql
-- SQL is declarative: you say what you want
SELECT productname, price
FROM products
WHERE price > 50
ORDER BY price DESC;

-- The database engine decides how to execute it.
-- You do not write loops or index lookups yourself.
```

## Performance / Optimization Notes

- SQL was invented in the 1970s at IBM. It became the standard database language in 1986.
- SQL is used for: reading data (SELECT), writing data (INSERT, UPDATE, DELETE), defining structure (CREATE, ALTER, DROP), and controlling access (GRANT, REVOKE).
- Learning SQL means learning to think in sets of rows, not one row at a time.

[[02-er-model]]
