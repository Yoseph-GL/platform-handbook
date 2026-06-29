# SQL Intermediate: Cardinality

## Architecture / Rationale

Cardinality defines how many rows in one table can relate to rows in another table. It is the foundation of table relationships and foreign key design.

Cardinality types:
- **One-to-One (1:1)**: one row in Table A links to exactly one row in Table B. Use a UNIQUE foreign key.
- **One-to-Many (1:N)**: one row in Table A links to many rows in Table B. This is the most common type.
- **Many-to-Many (M:N)**: many rows in Table A link to many rows in Table B. You need a join table.

## Query / Code Blocks

```sql
-- One-to-One (1:1): each employee has exactly one badge
-- The foreign key is also UNIQUE to enforce the 1:1 rule
CREATE TABLE employees (
    employeeid INT PRIMARY KEY,
    firstname VARCHAR(100) NOT NULL
);

CREATE TABLE badges (
    badgeid INT PRIMARY KEY,
    employeeid INT UNIQUE NOT NULL,
    badge_code VARCHAR(50),
    FOREIGN KEY (employeeid) REFERENCES employees(employeeid)
);
```

```sql
-- One-to-Many (1:N): one supplier has many products
-- This is the default relationship. No UNIQUE constraint on the foreign key.
CREATE TABLE suppliers (
    supplierid INT PRIMARY KEY,
    suppliername VARCHAR(100) NOT NULL
);

CREATE TABLE products (
    productid INT PRIMARY KEY,
    productname VARCHAR(100) NOT NULL,
    supplierid INT,
    FOREIGN KEY (supplierid) REFERENCES suppliers(supplierid)
);
```

```sql
-- Many-to-Many (M:N): one student can take many courses,
-- and one course can have many students.
-- You need a join table (enrollments) to connect them.
CREATE TABLE students (
    studentid INT PRIMARY KEY,
    studentname VARCHAR(100) NOT NULL
);

CREATE TABLE courses (
    courseid INT PRIMARY KEY,
    coursename VARCHAR(100) NOT NULL
);

CREATE TABLE enrollments (
    studentid INT,
    courseid INT,
    enrolled_date DATE NOT NULL,
    PRIMARY KEY (studentid, courseid),
    FOREIGN KEY (studentid) REFERENCES students(studentid),
    FOREIGN KEY (courseid) REFERENCES courses(courseid)
);

-- Find all courses a student is enrolled in
SELECT s.studentname, c.coursename
FROM students s
JOIN enrollments e ON s.studentid = e.studentid
JOIN courses c ON e.courseid = c.courseid
WHERE s.studentid = 1;
```

## Performance / Optimization Notes

- One-to-Many is the fastest relationship. The foreign key index on the "many" side makes JOINs efficient.
- Many-to-Many join tables need a composite primary key on both foreign columns. This prevents duplicate connections.
- Avoid storing relationships as comma-separated lists in a single column. It breaks foreign keys, indexing, and JOINs. Use a join table instead.
- When you see a 1:1 relationship, ask yourself if the two tables should be merged into one. 1:1 is rare and often signals over-normalization.

[[02-joins]]
[[05-normalization]]
[[02-er-model]]
