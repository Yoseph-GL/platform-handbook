# SQL Intermediate: Comments

## Architecture / Rationale

Comments document your queries for other developers and for your future self. The database engine ignores them during execution.

Comment rules:
- Use `--` for single-line comments. Everything after `--` on that line is ignored.
- Use `/* */` for multi-line comments. Everything between the markers is ignored.
- Write comments that explain *why*, not *what*. The SQL already shows what the query does.
- Keep comments up to date. An outdated comment is worse than no comment.

## Query / Code Blocks

```sql
-- ✅ Good comment: explains why the filter exists
-- Exclude test accounts from the report
SELECT customerid, companyname, country
FROM customers
WHERE customerid >= 100;

-- ✅ Good comment: documents a business rule
-- Discount only applies to active products with stock > 0
UPDATE products
SET price = price * 0.9
WHERE discontinued = 0
  AND units_in_stock > 0;
```

```sql
-- ❌ Bad comment: just repeats what the query already says
-- Select customerid, companyname, and country from customers
SELECT customerid, companyname, country
FROM customers;

-- ❌ Bad comment: outdated and misleading
-- Uses the old price column (price was renamed to unit_price last month)
SELECT productname, price
FROM products;
```

```sql
-- ❌ Commented-out code: never commit this to a shared repository
-- It confuses other developers. Nobody knows if it is still needed.
-- SELECT old_column FROM old_table WHERE condition = 'value';

-- ✅ If you must keep old logic, use a version control system like Git.
-- Delete the old code and rely on the commit history to recover it.
```

```sql
/* Multi-line comment example.
   Use this style for:
   - Long explanations.
   - Exercise descriptions.
   - Temporary notes during development. */

/*
📌 Exercise: count products per category.

Objective: show how many products exist in each category.
Columns needed: CategoryID and the count of products.

Hint: use the Products table, group by CategoryID, and apply COUNT(*).
*/

SELECT categoryid, COUNT(*) AS total_products
FROM products
GROUP BY categoryid;
```

## Performance / Optimization Notes

- Comments have zero impact on query performance. The parser removes them before execution.
- Do not embed sensitive information in comments. They are visible in query logs, execution plans, and backups.
- Keep comments up to date. An outdated comment that contradicts the query is worse than no comment at all.
- Use block comments (`/* */`) for section headers and exercise descriptions. Use line comments (`--`) for inline explanations.
