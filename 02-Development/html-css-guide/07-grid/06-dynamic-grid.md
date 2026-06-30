# CSS Grid: Dynamic Grid

## Architecture / Rationale

A dynamic grid adapts to the container size without media queries. It uses `auto-fill` or `auto-fit` with `minmax()` to add or remove columns automatically.

- The browser calculates how many columns fit based on the `minmax` minimum.
- As the container grows, more columns appear. As it shrinks, columns drop.
- This is the foundation of truly responsive component grids.

## Query / Code Blocks

```css
/* Dynamic card grid: 250px minimum, as many as fit */
.card-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
    gap: 24px;
}

/* auto-fit: empty columns collapse, items stretch */
.card-grid-fit {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 24px;
}

/* With max-width to limit growth on ultra-wide screens */
.card-grid-capped {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
    max-width: 1200px;
    margin: 0 auto;
}
```

## Performance / Optimization Notes

- `auto-fill` keeps empty columns. `auto-fit` collapses them and stretches existing items. The visual difference is subtle but important.
- Dynamic grids can replace most media query breakpoints for card layouts.
- Combine with `gap` for consistent spacing regardless of the column count.
