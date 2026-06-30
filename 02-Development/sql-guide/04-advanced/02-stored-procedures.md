# SQL Advanced: Stored Procedures

## Architecture / Rationale

A stored procedure is a block of SQL code saved on the database server. You call it by name and pass parameters. It can contain logic, validation, and multiple statements.

Procedure rules:
- Use procedures for business logic that must run close to the data.
- Validate all parameters before modifying data. Raise errors for invalid input.
- Use `COMMIT` inside the procedure to finalize changes, or let the caller manage the transaction.

## Query / Code Blocks

```sql
-- Procedure: apply a percentage discount to all products of one supplier
CREATE OR REPLACE PROCEDURE sp_aplicar_descuento_masivo(
    p_supplierid INT,
    p_porcentaje NUMERIC
)
    LANGUAGE plpgsql
AS $$
BEGIN
    -- Step 1: Validate business rules
    IF p_porcentaje <= 0 OR p_porcentaje > 50 THEN
        RAISE EXCEPTION 'Operation aborted: discount must be between 1%% and 50%%.';
    END IF;

    -- Step 2: Apply the discount
    UPDATE products
    SET price = price - (price * (p_porcentaje / 100.0))
    WHERE supplierid = p_supplierid;

    -- Step 3: Save the changes
    COMMIT;
END;
$$;

-- Call the procedure
CALL sp_aplicar_descuento_masivo(2, 15.0);
```

```sql
-- Procedure: register a reward for an employee with validation
CREATE OR REPLACE PROCEDURE sp_registrar_recompensa(
    p_employeeid INT,
    p_recompensa INT,
    p_mes TEXT
)
    LANGUAGE plpgsql
AS $$
DECLARE
    v_empleado_existe BOOLEAN;
BEGIN
    -- Step 1: Check that the employee exists
    SELECT EXISTS (
        SELECT 1 FROM employees WHERE employeeid = p_employeeid
    ) INTO v_empleado_existe;

    -- Step 2: Stop if the employee does not exist
    IF NOT v_empleado_existe THEN
        RAISE EXCEPTION 'Cannot insert reward. Employee ID % does not exist in the database.', p_employeeid;
    END IF;

    -- Step 3: Insert the reward safely
    INSERT INTO rewards (employeeid, reward, month)
    VALUES (p_employeeid, p_recompensa, p_mes);

    COMMIT;
END;
$$;

-- Valid call: employee 3 exists
CALL sp_registrar_recompensa(3, 500, 'July');

-- Invalid call: employee 999 does not exist, raises the controlled exception
CALL sp_registrar_recompensa(999, 1000, 'August');
```

## Performance / Optimization Notes

- Stored procedures run on the server. Push filtering, aggregation, and data validation into them to reduce network traffic.
- Use `RAISE EXCEPTION` for business rule violations. The caller gets a clear error message instead of corrupt data.
- Avoid long-running procedures that hold locks for many seconds. Split large batch updates into smaller chunks when possible.
- Test procedures with invalid parameters. Make sure every edge case produces a clear error, not a silent failure.

[[01-transactions-and-locks]]
[[03-user-defined-functions]]
