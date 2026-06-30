# CSS Grid: Creating a Grid

## Architecture / Rationale

Creating a Grid starts with defining the columns and rows. The `grid-template-columns` and `grid-template-rows` properties set the track sizes.

- Each value defines one track (column or row).
- Tracks can use `px`, `%`, `fr`, `auto`, or `minmax()`.
- `gap` sets the space between tracks (both columns and rows).

## Query / Code Blocks

```css
/* Three equal columns */
.grid-3-col {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 20px;
}

/* Two columns: sidebar 250px, main content fills the rest */
.layout {
    display: grid;
    grid-template-columns: 250px 1fr;
    gap: 24px;
}

/* Header, content, footer rows */
.page {
    display: grid;
    grid-template-rows: auto 1fr auto;
    min-height: 100vh;
}
```

## Performance / Optimization Notes

- Use `fr` units for flexible tracks. They distribute available space proportionally.
- Fixed pixel tracks (`200px`) are fine for sidebars. Use `fr` for the content area.
- `gap` replaces margin for grid spacing. It only applies between tracks, never at the edges.
