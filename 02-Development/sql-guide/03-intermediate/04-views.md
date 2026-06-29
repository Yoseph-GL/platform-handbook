# SQL Intermediate: Views

## Architecture / Rationale

A view is a saved SELECT query that you can query like a table. It does not store data — it runs the underlying query every time you use it.

View rules:
- Use views to simplify complex queries that you run often.
- Use views to hide columns from users who do not need them.
- Views are read-only in most databases (you cannot INSERT into them directly unless they meet special conditions).

## Query / Code Blocks

```sql
-- Create a view: simplified list of expensive products
CREATE VIEW simplified_products AS
    SELECT p.productid, p.productname, p.price
    FROM products p
    WHERE productid > 20
    ORDER BY productid DESC;

-- Query the view like a normal table
SELECT * FROM simplified_products;

-- Remove the view when it is no longer needed
DROP VIEW IF EXISTS simplified_products;
```

## Performance / Optimization Notes

- A view does not store data. Every time you query it, the database runs the full underlying SELECT. Check the execution plan before using a view in a high-traffic query.
- Nesting views (a view that queries another view) can hide performance problems. The planner may not optimize across multiple view layers well.
- For complex, frequently-used queries, consider a materialized view instead. It stores the result and refreshes on demand.
- Use `DROP VIEW IF EXISTS` in cleanup scripts. It avoids errors when the view was already removed.

[[01-subqueries]]
