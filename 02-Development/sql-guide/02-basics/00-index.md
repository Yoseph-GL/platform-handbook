# SQL Level 2: Basics

## Architecture / Rationale

This level defines baseline SQL operations required for day-to-day backend work.

Scope:
- Read queries (`SELECT`, filters, sorting, limits).
- Filter operators (`BETWEEN`, `LIKE`, `IN`, `IS NULL`, logic combinations).
- Identifiers, column aliases (`AS`), and table aliases.
- Aggregation patterns (`COUNT`, `SUM`, `AVG`, `GROUP BY`, `HAVING`).
- Expressions and null handling (`CASE`, `IFNULL`).
- Safe write operations (`INSERT`, `UPDATE`, `DELETE`).

## Query / Code Blocks

```sql
-- Module pages
-- [[01-select-filter-sort]]
-- [[02-aggregation-and-grouping]]
-- [[03-expressions-and-null-handling]]
-- [[04-safe-mutations]]
-- [[05-baseline-performance]]
-- [[06-filter-operators]]
-- [[07-identifiers-and-aliases]]
```

## Performance / Optimization Notes

- Keep basic queries explicit and bounded to avoid accidental hot-path regressions.
- Use this level as the minimum standard before moving into dedicated joins and advanced tuning modules.
