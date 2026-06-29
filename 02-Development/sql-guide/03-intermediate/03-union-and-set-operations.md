# SQL Intermediate: Union and Set Operations

## Architecture / Rationale

UNION combines the results of two or more SELECT queries into a single result set. Both queries must return the same number of columns with compatible data types.

Set operation rules:
- **UNION ALL** keeps all rows from both queries, including duplicates. It is fast.
- **UNION** removes duplicate rows. It does extra work to sort and deduplicate.
- The column names come from the first SELECT statement.

## Query / Code Blocks

```sql
-- UNION ALL: keeps duplicates. If 'Juan' appears in both blocks, it appears twice.
SELECT 'Juan' AS empleado, 'Soporte' AS departamento
UNION ALL
SELECT 'Juan' AS empleado, 'Soporte' AS departamento;

-- UNION: removes duplicates. The duplicate 'Juan' row is collapsed into one.
SELECT 'Juan' AS empleado, 'Soporte' AS departamento
UNION
SELECT 'Juan' AS empleado, 'Soporte' AS departamento;

-- UNION ALL with real tables: all employee IDs from two tables combined
-- Duplicates are kept (an employee appears once per order, not once total)
SELECT employeeid
FROM employees
UNION ALL
SELECT employeeid
FROM orders;

-- UNION with real tables: distinct employee IDs across both tables
-- Each employee ID appears only once
SELECT employeeid
FROM employees
UNION
SELECT employeeid
FROM orders;
```

## Performance / Optimization Notes

- Prefer UNION ALL over UNION when duplicates do not matter. It avoids the sort-and-dedup step and can be much faster on large result sets.
- UNION forces the database to compare every row to find duplicates. For big result sets, this can use a lot of memory and time.
- If you know the two sets have no overlap (for example, data from different regions), always use UNION ALL.
- The number and order of columns must match across all SELECT statements. If they do not, the query fails with a syntax error.

[[02-joins]]
