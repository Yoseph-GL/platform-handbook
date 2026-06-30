# SQL Roadmap: Future Themes

## Architecture / Rationale

This roadmap keeps the guide scalable without mixing advanced topics into the foundational levels.

Implemented:
1. ~~**Joins:** `INNER`, `LEFT`, `RIGHT`, `FULL`, `CROSS`~~ → [[03-intermediate/02-joins]]
2. ~~**Transactions:** isolation levels, lock behavior, deadlock patterns~~ → [[04-advanced/01-transactions-and-locks]]
3. ~~**Stored Procedures and UDFs**~~ → [[04-advanced/02-stored-procedures]], [[04-advanced/03-user-defined-functions]]

Planned progression:
1. **Indexing Deep Dive:** composite index design, covering indexes, cardinality analysis.
2. **Query Optimization:** plan regression controls and workload benchmarking.
3. **Operational SQL:** migrations at scale, backups, restore drills.

## Query / Code Blocks

```sql
-- Example placeholder for upcoming indexing deep dive
CREATE INDEX idx_orders_customer_date ON orders (customerid, orderdate);

EXPLAIN ANALYZE
SELECT o.orderid, o.orderdate, SUM(od.quantity)
FROM orders o
JOIN orderdetails od ON o.orderid = od.orderid
WHERE o.customerid = 5
GROUP BY o.orderid, o.orderdate;
```

## Performance / Optimization Notes

- Keep advanced topics isolated by level to preserve entry-level readability.
- Promote topics from roadmap to active modules only after baseline examples and performance checks are documented.
