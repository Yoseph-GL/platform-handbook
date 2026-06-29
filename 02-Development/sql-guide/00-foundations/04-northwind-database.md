# SQL Foundations: Northwind Database

## Architecture / Rationale

Northwind is a sample database created by Microsoft. It stores data for a fictional trading company. Most of the queries in this guide use Northwind tables.

Why Northwind:
- It is small enough to learn with but realistic enough to be useful.
- It has all the common relationship types (1:1, 1:N, M:N).
- It ships with many database tools, so you can load it quickly.

## Query / Code Blocks

```sql
-- Main Northwind tables used in this guide
-- customers:   companies that buy products
-- employees:   people who work at Northwind
-- orders:      sales orders placed by customers
-- orderdetails: line items inside each order
-- products:    items available for sale
-- suppliers:   companies that provide products
-- categories:  product groupings (beverages, condiments, etc.)

-- Example: find all orders for a specific customer
SELECT o.orderid, o.orderdate, c.companyname
FROM orders o
JOIN customers c ON o.customerid = c.customerid
WHERE c.companyname = 'Alfreds Futterkiste';

-- Example: find the top 5 best-selling products
SELECT p.productname, SUM(od.quantity) AS total_sold
FROM products p
JOIN orderdetails od ON p.productid = od.productid
GROUP BY p.productid
ORDER BY total_sold DESC
LIMIT 5;
```

## Performance / Optimization Notes

- Northwind tables are small by design. Queries run fast even without indexes. In production, you would add indexes on foreign key columns.
- Use Northwind to practice before trying queries on your own database. The data is safe to modify and easy to restore.
- The schema follows 3NF (Third Normal Form). Study it as an example of good database design.

[[03-first-steps]]
[[02-er-model]]
[[03-intermediate/05-normalization]]
