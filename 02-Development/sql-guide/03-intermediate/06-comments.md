# SQL Intermediate: Comments

## Architecture / Rationale

Comments document your queries for other developers and for your future self. The database engine ignores them during execution.

Comment rules:
- Use `--` for single-line comments. Everything after `--` on that line is ignored.
- Use `/* */` for multi-line comments. Everything between the markers is ignored.
- Write comments that explain *why*, not *what*. The SQL already shows what the query does.

## Query / Code Blocks

```sql
-- This is a single-line comment
SELECT productname, price
FROM products
WHERE price > 40;

/* This is a multi-line comment.
   It can span several lines.
   Use it for longer explanations or exercise descriptions. */

/*
📌 Exercise example documented with a block comment:

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
- Do not embed sensitive information in comments. They are visible in query logs and execution plans.
- Keep comments up to date. An outdated comment that contradicts the query is worse than no comment at all.
