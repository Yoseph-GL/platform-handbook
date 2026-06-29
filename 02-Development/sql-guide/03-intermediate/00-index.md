# SQL Level 3: Intermediate

## Architecture / Rationale

This level covers queries that combine and transform data across multiple tables.

Scope:
- Subqueries in SELECT, WHERE, and FROM clauses.
- Joins of all types (INNER, LEFT, RIGHT, FULL, CROSS).
- Set operations with UNION and UNION ALL.
- Views for reusable query definitions.
- Normalization principles for clean schema design.
- SQL comment syntax.

## Query / Code Blocks

```sql
-- Module pages
-- 01-subqueries.md
-- 02-joins.md
-- 03-union-and-set-operations.md
-- 04-views.md
-- 05-normalization.md
-- 06-comments.md
```

## Performance / Optimization Notes

- Prefer JOINs over correlated subqueries when the optimizer can merge them into a single scan.
- Use UNION ALL instead of UNION when duplicates are acceptable — it skips the sort-and-dedup step.
- Views do not store data; they run the underlying query every time. Check the execution plan before using them in hot paths.
