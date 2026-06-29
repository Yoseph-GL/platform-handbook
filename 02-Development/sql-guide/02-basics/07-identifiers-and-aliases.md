# SQL Basics: Identifiers and Aliases

## Architecture / Rationale

Identifiers are the names you give to databases, tables, and columns. Aliases let you rename columns or tables inside a query without changing the underlying schema.

Identifier rules:
- Use descriptive names in snake_case (`customer_id`, `order_date`).
- Avoid SQL reserved words as identifiers (`order`, `group`, `select`).
- Quote identifiers with double quotes only when necessary (spaces or reserved words).

Alias rules:
- Use `AS` to rename a column in the result set.
- Use a table alias to shorten long table names in JOINs.
- Aliases exist only for the duration of the query.

## Query / Code Blocks

```sql
-- Column alias with AS: rename a column in the output
SELECT unit AS quantity_left
FROM products;

-- Column alias without AS (works but less readable — use AS for clarity)
SELECT unit quantity_left
FROM products;

-- Multiple aliases in one query
SELECT productname AS name,
       price AS current_price,
       units_in_stock AS stock
FROM products
WHERE units_in_stock > 0;
```

```sql
-- Table alias: shorter name for the table in the query
SELECT p.productname, p.price, s.suppliername
FROM products AS p
JOIN suppliers AS s ON p.supplierid = s.supplierid;

-- Table alias is required in self-joins (same table appears twice)
-- Without aliases, the database cannot tell the two copies apart.
```

```sql
-- DISTINCT: removes duplicate rows from the result
SELECT DISTINCT country
FROM customers
ORDER BY country;

-- DISTINCT with multiple columns: unique combinations
SELECT DISTINCT country, city
FROM customers
ORDER BY country, city;

-- DISTINCT vs NOT: they are completely different things
-- DISTINCT removes duplicate rows (a SELECT modifier).
-- NOT negates a condition (a WHERE operator).

-- This query removes duplicate product names
SELECT DISTINCT productname
FROM products
ORDER BY productname DESC;

-- This query filters rows where the condition is false
SELECT productname
FROM products
WHERE NOT discontinued = 1;
```

## Performance / Optimization Notes

- `DISTINCT` forces a sort or hash operation to find duplicates. On large result sets, this can be expensive. Use it only when you really need unique rows.
- Table aliases make queries shorter but not faster. The query planner ignores them after parsing.
- Column aliases in WHERE clauses do not work. The WHERE runs before the SELECT list is evaluated. Repeat the full expression in WHERE or use a subquery.
- Avoid using SQL reserved words as identifiers. If you must, always quote them with double quotes.

[[01-select-filter-sort]]
[[06-filter-operators]]
