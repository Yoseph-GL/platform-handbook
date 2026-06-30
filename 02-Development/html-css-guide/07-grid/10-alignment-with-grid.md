# CSS Grid: Alignment with Grid

## Architecture / Rationale

Grid has six alignment properties, similar to Flexbox. They control where items sit inside their grid cells and how tracks distribute extra space.

Container properties:
- `justify-content` — aligns columns horizontally when they are smaller than the container.
- `align-content` — aligns rows vertically when they are smaller than the container.
- `justify-items` — aligns items horizontally inside their cells.
- `align-items` — aligns items vertically inside their cells.

Item properties:
- `justify-self` / `align-self` — overrides for a single item.

## Query / Code Blocks

```css
.grid {
    display: grid;
    grid-template-columns: repeat(3, 200px);
    grid-template-rows: repeat(2, 200px);
    gap: 16px;

    /* Center the whole grid in the container */
    justify-content: center;
    align-content: center;

    /* Center items inside their cells */
    justify-items: center;
    align-items: center;
}

/* One item aligned differently */
.item--corner {
    justify-self: end;
    align-self: start;
}
```

## Performance / Optimization Notes

- `justify-items` and `align-items` apply to every item. Use them to set the default for the whole grid.
- `stretch` (the default) makes items fill their cells. This is usually what you want.
- Use `place-items: center` as a shorthand to center content both ways inside cells.
