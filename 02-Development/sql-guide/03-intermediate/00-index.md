# SQL Level 3: Intermediate

## Architecture / Rationale

This level covers queries that combine and transform data across multiple tables.

Scope:
- Subqueries in SELECT, WHERE, and FROM clauses.
- Joins of all types (INNER, LEFT, RIGHT, FULL, CROSS).
- Set operations with UNION and UNION ALL.
- Views for reusable query definitions.
- Normalization principles for clean schema design.
- SQL comment syntax and best practices.
- Cardinality and table relationships (1:1, 1:N, M:N).

## Query / Code Blocks

```sql
-- Module pages
-- [[01-subqueries]]
-- [[02-joins]]
-- [[03-union-and-set-operations]]
-- [[04-views]]
-- [[05-normalization]]
-- [[06-comments]]
-- [[07-cardinality]]
```

## Performance / Optimization Notes

- Prefer JOINs over correlated subqueries when the optimizer can merge them into a single scan.
- Use UNION ALL instead of UNION when duplicates are acceptable — it skips the sort-and-dedup step.
- Views do not store data; they run the underlying query every time. Check the execution plan before using them in hot paths.
