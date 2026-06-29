# SQL Level 4: Advanced

## Architecture / Rationale

This level covers server-side logic and data integrity under concurrent access.

Scope:
- Transactions and locks for safe concurrent writes.
- Stored procedures for reusable, validated business logic.
- User-defined functions (UDFs) for computed values and parameterized result sets.

## Query / Code Blocks

```sql
-- Module pages
-- 01-transactions-and-locks.md
-- 02-stored-procedures.md
-- 03-user-defined-functions.md
```

## Performance / Optimization Notes

- Keep transactions short to reduce lock contention.
- Stored procedures run on the server — push filtering and aggregation inside them to avoid sending large result sets over the network.
- Scalar UDFs can force row-by-row execution in some engines. Test with realistic data volumes before relying on them in production queries.
