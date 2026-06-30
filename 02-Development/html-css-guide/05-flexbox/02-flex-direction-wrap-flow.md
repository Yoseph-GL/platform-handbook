# CSS Flexbox: Flex Direction, Wrap and Flow

## Architecture / Rationale

These properties control the direction of the flex items and whether they wrap to the next line.

- `flex-direction`: `row` (default), `row-reverse`, `column`, `column-reverse`.
- `flex-wrap`: `nowrap` (default), `wrap`, `wrap-reverse`.
- `flex-flow`: shorthand for `flex-direction` + `flex-wrap`.

## Query / Code Blocks

```css
/* Row (default): items flow left to right */
.row {
    display: flex;
    flex-direction: row;
}

/* Column: items stack top to bottom */
.column {
    display: flex;
    flex-direction: column;
}

/* Row with wrapping: items move to the next line when out of space */
.wrap {
    display: flex;
    flex-wrap: wrap;
    gap: 16px;
}

/* Shorthand: direction + wrap */
.flow {
    flex-flow: row wrap;
}
```

## Performance / Optimization Notes

- Use `flex-direction: column` on small screens to stack elements vertically without media queries.
- `wrap` is essential for image galleries. Images flow to the next row naturally.
- Avoid `row-reverse` and `column-reverse`. They confuse screen readers because the visual order differs from the DOM order.
