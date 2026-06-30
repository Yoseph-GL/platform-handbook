# CSS Advanced: Min-content, Max-content and Fit-content

## Architecture / Rationale

These sizing keywords tell the browser to size an element based on its content, not a fixed value. They are powerful tools for intrinsic web design.

- `min-content`: the smallest size the content can be without overflowing (the longest word defines the width).
- `max-content`: the size the content would be if it never wrapped (all text on one line).
- `fit-content`: sizes to the content but caps at a maximum value.

## Query / Code Blocks

```css
/* Column that fits the longest word */
.sidebar {
    width: min-content;
}

/* Column that fits all text on one line */
.nowrap-column {
    width: max-content;
}

/* Element that sizes to content but never exceeds the container */
.card {
    width: fit-content;
    max-width: 100%;
    margin: 0 auto;
}

/* Grid column that fits its content */
.grid-auto {
    display: grid;
    grid-template-columns: min-content 1fr min-content;
    /* First and last columns size to content. Middle fills the rest. */
}
```

## Performance / Optimization Notes

- `min-content` is useful for icon columns or label columns. They shrink to the minimum needed width.
- `fit-content` is a safer version of `max-content`. It respects the parent container bounds.
- These keywords work in `width`, `height`, `grid-template-columns`, and `grid-template-rows`.
