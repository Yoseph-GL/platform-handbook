# CSS Flexbox: Alignment on Axes

## Architecture / Rationale

Flexbox has four alignment properties. Two control the main axis, two control the cross axis. They are the key to centering and distributing space.

- **Main axis**: `justify-content` (container) — distributes items along the row/column.
- **Cross axis**: `align-items` (container) — aligns items along the perpendicular axis.
- **Cross axis per item**: `align-self` (item) — overrides `align-items` for one item.
- **Multi-line cross axis**: `align-content` — distributes space between wrapped rows.

## Query / Code Blocks

```css
.container {
    display: flex;
    /* Center items horizontally */
    justify-content: center;
    /* Center items vertically */
    align-items: center;
}

/* Common values for justify-content */
/* flex-start | flex-end | center | space-between | space-around | space-evenly */

/* Common values for align-items */
/* flex-start | flex-end | center | stretch | baseline */
```

## Performance / Optimization Notes

- `justify-content: space-between` is the standard way to push a logo left and navigation links right.
- Use `align-items: center` to vertically center text next to an icon or image.
- Avoid `space-around` for grids. The outer gaps are half the inner gaps, which looks uneven.
