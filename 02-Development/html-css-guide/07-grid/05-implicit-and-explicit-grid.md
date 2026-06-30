# CSS Grid: Implicit and Explicit Grid

## Architecture / Rationale

Grid distinguishes between tracks you define (explicit) and tracks the browser creates automatically (implicit). Understanding this difference prevents layout surprises.

- **Explicit grid**: columns and rows you define with `grid-template-*`.
- **Implicit grid**: extra rows or columns the browser creates when items exceed your definition.
- Control implicit tracks with `grid-auto-rows` and `grid-auto-columns`.

## Query / Code Blocks

```css
/* Explicit: 2 columns defined. Implicit: rows created as needed. */
.grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-auto-rows: 150px;
    gap: 16px;
}

/* Explicit rows + implicit rows have different heights */
.grid-mixed {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 200px 200px;  /* First two rows */
    grid-auto-rows: 100px;            /* All additional rows */
}
```

## Performance / Optimization Notes

- Always set `grid-auto-rows` when you expect more items than defined rows. Otherwise, rows size to content and may be uneven.
- The implicit grid starts when items run out of explicitly defined tracks. Think of it as the "overflow" of Grid.
- Use `grid-auto-flow: column` to make the implicit grid create columns instead of rows.
