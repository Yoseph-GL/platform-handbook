# CSS Grid: Grid Column and Grid Row

## Architecture / Rationale

`grid-column` and `grid-row` let you place items on specific grid lines. You can span items across multiple columns or rows.

- Grid lines are numbered starting from 1 (and -1 from the end).
- `grid-column: 1 / 3` spans from line 1 to line 3 (two columns).
- `grid-row: span 2` spans two rows from the item's auto-placement position.

## Query / Code Blocks

```css
.grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-template-rows: repeat(3, 150px);
    gap: 16px;
}

/* Hero item: spans two columns and two rows */
.item--hero {
    grid-column: 1 / 3;
    grid-row: 1 / 3;
}

/* Wide item: spans full width */
.item--wide {
    grid-column: 1 / -1;
}

/* Tall item: spans two rows from current position */
.item--tall {
    grid-row: span 2;
}
```

## Performance / Optimization Notes

- Use line numbers for precise placement. Use `span` when you only care about the size, not the position.
- `1 / -1` means "first line to last line". It is the standard way to span the full width of a grid.
- Avoid placing items with line numbers when order matters. Changing the HTML becomes harder because positions are hardcoded.
