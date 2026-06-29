# SQL Advanced: User-Defined Functions

## Architecture / Rationale

A user-defined function (UDF) is a reusable block of code that returns a value or a table. Unlike stored procedures, you can use UDFs directly inside SELECT statements.

UDF types:
- **Scalar UDF**: returns a single value. Use it in SELECT, WHERE, or ORDER BY.
- **Table-returning UDF**: returns a set of rows. Query it like a table.

UDF rules:
- Functions must be deterministic when possible (same input always gives the same output).
- Do not change data inside a function (no INSERT, UPDATE, DELETE). Use a procedure for that.

## Query / Code Blocks

```sql
-- Scalar UDF: calculate tax for a given price
CREATE OR REPLACE FUNCTION fn_calcular_iva(p_precio NUMERIC)
    RETURNS NUMERIC
    LANGUAGE plpgsql
AS $$
BEGIN
    RETURN p_precio * 1.16;
END;
$$;

-- Use the scalar function in a SELECT
SELECT productname,
       price AS precio_base,
       fn_calcular_iva(price) AS precio_con_impuesto
FROM products;
```

```sql
-- Table-returning UDF: get all products in a given category
CREATE OR REPLACE FUNCTION fn_obtener_productos_por_categoria(p_cat_id INT)
    RETURNS TABLE (id_producto INT, nombre_producto TEXT, precio_actual NUMERIC)
    LANGUAGE plpgsql
AS $$
BEGIN
    RETURN QUERY
        SELECT productid, productname, price
        FROM products
        WHERE categoryid = p_cat_id;
END;
$$;

-- Query the table-returning function like a regular table
SELECT * FROM fn_obtener_productos_por_categoria(3);
```

## Performance / Optimization Notes

- Scalar UDFs can force row-by-row execution in some database engines. On large tables, this can be much slower than writing the calculation inline. Test with realistic data volumes.
- Table-returning UDFs are generally well optimized. The planner can push WHERE conditions into the function in many cases.
- Avoid calling scalar UDFs inside WHERE clauses on large tables. The function runs once per row, which prevents index usage.
- Mark functions as `IMMUTABLE` or `STABLE` when they qualify. This lets the planner cache results and optimize better.

[[02-stored-procedures]]
