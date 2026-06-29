# SQL Foundations: ER Model (Chen Notation)

## Architecture / Rationale

The Entity-Relationship (ER) Model is a way to design databases visually. You draw entities (tables), attributes (columns), and relationships (foreign keys) before writing any SQL.

Chen Notation rules:
- **Entities** are drawn as rectangles. Each entity becomes a table.
- **Attributes** are drawn as ovals connected to their entity. Each attribute becomes a column.
- **Relationships** are drawn as diamonds between entities. Each relationship becomes a foreign key or a join table.
- Primary key attributes are underlined.

## Query / Code Blocks

```sql
-- Example: an ER diagram with two entities and one relationship
--
--   ┌─────────────┐          ┌─────────────┐
--   │  Supplier   │          │   Product   │
--   ├─────────────┤          ├─────────────┤
--   │ supplierid  │───┬──────│ productid   │
--   │ suppliername│   │      │ productname │
--   │ city        │   │      │ price       │
--   └─────────────┘   │      │ supplierid  │
--                      └──────│             │
--                supplies    └─────────────┘
--
-- The diamond "supplies" is a 1:N relationship:
-- one supplier supplies many products.

CREATE TABLE suppliers (
    supplierid INT PRIMARY KEY,
    suppliername VARCHAR(100) NOT NULL,
    city VARCHAR(100)
);

CREATE TABLE products (
    productid INT PRIMARY KEY,
    productname VARCHAR(100) NOT NULL,
    price NUMERIC,
    supplierid INT,
    FOREIGN KEY (supplierid) REFERENCES suppliers(supplierid)
);
```

## Performance / Optimization Notes

- Draw the ER diagram before writing CREATE TABLE statements. It helps you find missing relationships and duplicate columns.
- Every relationship in the diagram becomes a foreign key in the SQL schema. Do not skip this step.
- For Many-to-Many relationships, the diamond becomes a join table with a composite primary key.
- Chen Notation is one of several diagram styles. Others include Crow's Foot and UML. The concepts are the same across all styles.

[[01-what-is-sql]]
[[03-first-steps]]
[[03-intermediate/07-cardinality]]
