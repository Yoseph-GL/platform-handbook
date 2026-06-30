# CSS Grid: Repeat and Minmax

## Architecture / Rationale

`repeat()` and `minmax()` make Grid definitions shorter and more powerful. They are essential for creating flexible, responsive grids.

- `repeat(count, size)`: repeats a track definition. `repeat(3, 1fr)` equals `1fr 1fr 1fr`.
- `minmax(min, max)`: sets a size range for a track. The track never goes below `min` or above `max`.
- Combine them: `repeat(auto-fill, minmax(250px, 1fr))` creates a responsive grid without media queries.

## Query / Code Blocks

```css
/* 12 equal columns */
.grid-12 {
    display: grid;
    grid-template-columns: repeat(12, 1fr);
}

/* Columns between 250px and 1fr, as many as fit */
.grid-responsive {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
    gap: 16px;
}

/* Mixed: fixed sidebar with repeat for the rest */
.layout {
    display: grid;
    grid-template-columns: 250px repeat(3, 1fr);
}
```

## Performance / Optimization Notes

- `repeat(auto-fill, minmax(250px, 1fr))` is the most powerful pattern in CSS. It creates a responsive grid with zero media queries.
- `auto-fill` adds empty tracks to fill the row. `auto-fit` collapses empty tracks so items stretch. Choose based on whether you want empty space or stretched items.
- `minmax(0, 1fr)` prevents content from overflowing the track. The `0` tells the browser the track can shrink to nothing.
