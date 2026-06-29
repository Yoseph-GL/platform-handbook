# SQL Intermediate: Subqueries

## Architecture / Rationale

A subquery is a query inside another query. You can use subqueries in three places: the SELECT list, the WHERE clause, and the FROM clause.

Subquery rules:
- A scalar subquery returns exactly one value (one row, one column). Use it in SELECT or WHERE.
- A correlated subquery references a column from the outer query. It runs once per outer row.
- A derived table is a subquery in the FROM clause. It acts like a temporary table for the outer query.

## Query / Code Blocks

```sql
-- Correlated subquery in SELECT: get the product name for each order detail row
SELECT productid,
       quantity,
       (SELECT productname
        FROM products
        WHERE products.productid = orderdetails.productid) AS name,
       (SELECT price
        FROM products
        WHERE products.productid = orderdetails.productid) AS price
FROM orderdetails;

-- Subquery in WHERE: only show products where price is above 40
SELECT productid,
       SUM(quantity) AS sale,
       ROUND(SUM(quantity) * (SELECT price
                              FROM products
                              WHERE orderdetails.productid = products.productid))
           AS total_collected
FROM orderdetails
WHERE (SELECT price
       FROM products
       WHERE orderdetails.productid = products.productid) > 40
GROUP BY productid
ORDER BY total_collected DESC;

-- Derived table: subquery in FROM, filtered again by the outer query
SELECT productname, total_collected
FROM (SELECT productid,
             SUM(quantity) AS sale,
             (SELECT productname
              FROM products
              WHERE products.productid = orderdetails.productid) AS productname,
             (SELECT price
              FROM products
              WHERE products.productid = orderdetails.productid) AS price,
             ROUND(SUM(quantity) * (SELECT price
                                    FROM products
                                    WHERE products.productid = orderdetails.productid),
                   2) AS total_collected
      FROM orderdetails
      GROUP BY productid
      ORDER BY total_collected DESC)
WHERE price > 100;

-- Multi-level nesting: employees with total sales below the average
-- The inner subquery calculates total units sold per employee.
-- The middle subquery calculates the average of those totals.
-- The outer query returns only employees below that average.
SELECT FirstName,
       LastName,
       total_units
FROM (
         SELECT e.FirstName,
                e.LastName,
                (SELECT SUM(od.quantity)
                 FROM orders o,
                      orderdetails od
                 WHERE o.employeeid = e.employeeid
                   AND od.orderid = o.orderid) AS total_units
         FROM employees e) AS VentasIndividuales
WHERE total_units < (
    SELECT AVG(total_units)
    FROM (
             SELECT (SELECT SUM(od2.quantity)
                     FROM orders o2,
                          orderdetails od2
                     WHERE o2.employeeid = e2.employeeid
                       AND od2.orderid = o2.orderid) AS total_units
             FROM employees e2) AS PromedioGlobal);
```

## Performance / Optimization Notes

- Correlated subqueries in SELECT run once for every row in the outer query. On large tables, this becomes slow. Rewrite them as JOINs when possible.
- Subqueries in WHERE with `IN` or `EXISTS` are usually well optimized by the query planner.
- Derived tables (subqueries in FROM) do not have indexes. If the inner query returns many rows, the outer filter scans everything. Use a CTE or a temporary table for complex cases.
- Avoid repeating the same correlated subquery multiple times in one SELECT. Compute it once in a derived table or CTE instead.

[[02-joins]]
