# CSS Grid: Grid Flow Dense

## Architecture / Rationale

`grid-auto-flow` controls how auto-placed items fill the grid. The default is `row` — items fill row by row. `dense` tells the browser to fill holes with smaller items.

- `grid-auto-flow: row` (default) — items flow left to right, row by row. Gaps may appear.
- `grid-auto-flow: dense` — the browser backfills gaps with items that fit. No empty holes.
- Dense packing changes the visual order. Use only when the visual order does not matter.

## Query / Code Blocks

```css
/* Default: items placed in DOM order, gaps may appear */
.gallery {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-auto-flow: row;
}

/* Dense: browser fills all holes */
.gallery-dense {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-auto-flow: dense;
}

.item--large {
    grid-column: span 2;
    grid-row: span 2;
}
```

## Performance / Optimization Notes

- `dense` can move items visually far from their DOM position. Screen readers follow the DOM order, creating a mismatch.
- Use `dense` for image galleries where visual order is not critical.
- Avoid `dense` for content that has a logical reading order (articles, forms, navigation).
