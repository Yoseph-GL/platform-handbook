# SQL Basics: Filter Operators

## Architecture / Rationale

Filter operators let you write precise WHERE clauses. They go beyond simple equals and range checks.

Operator rules:
- Use `BETWEEN` for inclusive range checks (it includes both endpoints).
- Use `LIKE` for pattern matching on text columns.
- Use `IN` for lists of allowed values.
- Use `IS NULL` to check for missing data (not `= NULL`).
- Group AND/OR logic with parentheses to make the intent clear.

## Query / Code Blocks

```sql
-- AND: all conditions must be true
SELECT *
FROM customers
WHERE customerid >= 50
  AND customerid <= 55;

-- OR: at least one condition must be true
SELECT *
FROM employees
WHERE firstname = 'Nancy'
   OR firstname = 'Laura';

-- Combine AND and OR with parentheses for correct grouping
SELECT *
FROM products
WHERE (price > 20 OR categoryid = 6)
  AND supplierid = 7;

-- NOT: negate a condition
SELECT *
FROM customers
WHERE NOT country = 'USA'
  AND NOT country = 'France';

-- Multiple NOTs chained together
SELECT *
FROM customers
WHERE customerid >= 50
  AND NOT country = 'Germany'
  AND NOT country = 'Argentina'
  AND NOT country = 'Mexico'
  AND NOT country = 'USA'
  AND NOT country = 'France'
  AND NOT country = 'UK'
LIMIT 5;

-- BETWEEN: inclusive range (start AND end are both included)
SELECT *
FROM customers
WHERE NOT customerid BETWEEN 50 AND 55
  AND NOT country = 'Germany';

-- BETWEEN works with dates too
SELECT *
FROM employees
WHERE birthdate BETWEEN '1960-01-01' AND '2006-09-20';

-- LIKE: pattern matching with wildcards
-- % matches any number of characters
SELECT *
FROM employees
WHERE lastname LIKE '%r%';

-- _ matches exactly one character
-- This finds firstnames that are NOT 4 chars starting with any 2 chars, then "se", then 1 char
SELECT *
FROM employees
WHERE NOT firstname LIKE '__se%';

-- IS NULL: find rows with missing data
-- Never use = NULL — it does not work in SQL
SELECT *
FROM employees
WHERE firstname IS NULL
ORDER BY firstname;

-- IS NOT NULL: exclude rows with missing data
SELECT *
FROM employees
WHERE firstname IS NOT NULL
ORDER BY firstname;

-- IN: match any value in a list
SELECT *
FROM products
WHERE supplierid IN (3, 4, 5, 6)
ORDER BY productname;

-- IN works with text values too
SELECT *
FROM employees
WHERE firstname IN ('Joseph')
  AND lastname IN ('Garza');

-- Multiple values in IN
SELECT *
FROM employees
WHERE firstname IN ('Joseph', 'Ana');

-- NOT IN: exclude values in the list
SELECT *
FROM employees
WHERE firstname NOT IN ('Joseph', 'Ana');

-- ⚠️ Double NOT: the two NOTs cancel each other out
-- This query behaves exactly the same as WHERE firstname IN ('Joseph', 'Ana')
SELECT *
FROM employees
WHERE NOT firstname NOT IN ('Joseph', 'Ana');

-- ⚠️ Confusing boolean expression — avoid writing conditions like this
-- TRUE = TRUE is always true, TRUE != FALSE is always true
-- The OR FALSE = TRUE adds nothing
-- This returns the same rows as SELECT * FROM customers (no filter at all)
SELECT *
FROM customers
WHERE TRUE = TRUE AND TRUE != FALSE
   OR FALSE = TRUE;
```

## Performance / Optimization Notes

- `LIKE` with a leading `%` (`'%text'`) cannot use a regular index. Consider full-text search for large text columns.
- `IN` with a short list is fast. With hundreds of values, the optimizer may switch to a slower strategy.
- `IS NULL` checks are indexable. Use them freely in WHERE clauses.
- `NOT IN` can produce unexpected results when the sub-select or list contains NULL values. If any value in the list is NULL, the whole `NOT IN` returns empty.
- Group complex conditions with parentheses. It helps both the reader and the query planner.

[[01-select-filter-sort]]
