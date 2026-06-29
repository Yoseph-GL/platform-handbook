# SQL Intermediate: Normalization

## Architecture / Rationale

Normalization is the process of organizing data to reduce redundancy and prevent anomalies. It splits large tables into smaller, related tables.

Normal forms:
- **1NF (First Normal Form)**: Each cell holds one value. No repeating groups.
- **2NF (Second Normal Form)**: 1NF plus every non-key column depends on the whole primary key.
- **3NF (Third Normal Form)**: 2NF plus no non-key column depends on another non-key column.

Benefits:
- No duplicate data. You store each fact in one place.
- Updates are safe. You change one row, not many.
- Deletes do not accidentally destroy unrelated data.

## Query / Code Blocks

```sql
-- Example of a denormalized table (not recommended):
-- This table repeats supplier information for every product.
-- Updating a supplier name means changing it in many rows.
CREATE TABLE products_denormalized (
    productid INT,
    productname VARCHAR(100),
    suppliername VARCHAR(100),
    suppliercity VARCHAR(100)
);

-- Normalized version (recommended):
-- Supplier data lives in its own table. One update changes it everywhere.
CREATE TABLE suppliers (
    supplierid INT PRIMARY KEY,
    suppliername VARCHAR(100),
    city VARCHAR(100)
);

CREATE TABLE products (
    productid INT PRIMARY KEY,
    productname VARCHAR(100),
    supplierid INT,
    FOREIGN KEY (supplierid) REFERENCES suppliers(supplierid)
);
```

## Performance / Optimization Notes

- Normalization reduces write anomalies but can increase the number of JOINs in read queries. This is usually the right trade-off.
- Measure query performance before denormalizing. Many JOINs across indexed foreign keys are fast.
- Denormalize only when you have a proven performance problem that normalization causes.
- The Northwind database used throughout this guide is a good example of 3NF design.

[[02-joins]]
[[01-schema-foundations]]
