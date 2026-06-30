# CSS Grid: Subgrid

## Architecture / Rationale

`subgrid` lets a nested grid inherit the track sizes of its parent grid. This solves the problem of aligning content across separate grid containers.

- Without subgrid, each grid container calculates its own track sizes independently.
- With `subgrid`, the child grid uses the parent's column or row definitions.
- Useful for card components that need to align internal sections across a row.

## Query / Code Blocks

```css
/* Parent grid: defines column sizes */
.card-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 24px;
}

/* Child: uses subgrid to inherit parent's columns */
.card {
    display: grid;
    grid-row: span 1;
    /* Inherit columns from the parent grid */
    grid-template-columns: subgrid;
    gap: 0;
}

/* Card sections align across different cards */
.card__title { grid-column: 1; }
.card__body  { grid-column: 1; }
.card__button { grid-column: 1; align-self: end; }
```

## Performance / Optimization Notes

- Subgrid is supported in all modern browsers (Chrome 117+, Safari 16+, Firefox 71+).
- Only use subgrid when you need alignment across sibling grid items. For independent nested grids, regular Grid is simpler.
- Subgrid can inherit from `grid-template-columns`, `grid-template-rows`, or both. Specify which with `subgrid` in the respective property.
