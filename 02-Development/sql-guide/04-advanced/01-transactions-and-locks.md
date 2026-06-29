# SQL Advanced: Transactions and Locks

## Architecture / Rationale

A transaction groups several SQL statements into one unit of work. Either all statements succeed, or none of them do. This keeps the database consistent even when something fails.

Transaction rules:
- Start with `BEGIN`. The database records changes in a temporary space.
- End with `COMMIT` to save all changes permanently.
- End with `ROLLBACK` to discard all changes since the BEGIN.
- Between BEGIN and COMMIT, other users see the old data (depending on the isolation level).

## Query / Code Blocks

```sql
-- A safe transaction: order + order details as one atomic unit
BEGIN;

-- Step 1: create the order header
INSERT INTO orders (customerid, employeeid, orderdate)
VALUES (5, 3, '2026-06-28');

-- Step 2: add the line items
INSERT INTO orderdetails (orderid, productid, quantity)
VALUES (10250, 11, 2);

-- If both inserts worked, save them permanently
COMMIT;

-- If either insert failed, the application should run ROLLBACK instead.
-- ROLLBACK undoes everything back to the BEGIN.
```

```sql
-- Optimistic locking: prevent two users from overwriting each other
-- The version column acts as a counter. Each update checks that the version
-- has not changed since the row was read.
UPDATE products
SET price = 25, version = 2
WHERE productid = 11 AND version = 1;

-- If zero rows were updated, another user changed the row first.
-- The application should re-read the row and try again.
```

```sql
-- ⚠️ Common mistake: ROLLBACK cannot undo DDL statements
-- DROP TABLE, CREATE TABLE, ALTER TABLE are auto-committed in most databases.
-- The ROLLBACK below does nothing because the DROP was already permanent.

BEGIN;
DROP TABLE products CASCADE;
COMMIT;

ROLLBACK;  -- ❌ The table is already gone. This ROLLBACK has no effect.
```

## Performance / Optimization Notes

- Keep transactions short. The longer a transaction stays open, the longer locks are held and the more other users are blocked.
- Never wait for user input inside a transaction. Read data, get user confirmation, then open the transaction only for the writes.
- Use optimistic locking (version column) for low-contention data. It avoids holding locks while users think.
- Use explicit locking (`SELECT ... FOR UPDATE`) for high-contention data where conflicts are frequent.
- Test your transaction logic under concurrent load. Bugs in transaction handling only appear when multiple users hit the same rows at the same time.

[[02-stored-procedures]]
