# SQL Level 1: Structure

## Architecture / Rationale

This level defines clean, scalable database structure patterns for production systems.

Goals:
- Enforce integrity with constraints, not application-only logic.
- Keep schema naming and evolution deterministic.
- Prevent duplicate relationships and orphan records.

## Query / Code Blocks

```sql
-- Module pages
-- [[01-schema-foundations]]
-- [[02-constraints-and-keys]]
-- [[03-relationships-and-join-tables]]
-- [[04-schema-changes-and-versioning]]
-- [[05-clean-database-checklist]]
```

## Performance / Optimization Notes

- Structural decisions define query performance ceilings.
- Correct keys and constraints reduce full scans, duplicate writes, and data cleanup cost.
