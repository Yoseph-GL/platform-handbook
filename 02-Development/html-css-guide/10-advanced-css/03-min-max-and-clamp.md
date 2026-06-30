# CSS Advanced: Min, Max and Clamp

## Architecture / Rationale

`min()`, `max()`, and `clamp()` are CSS math functions that let you set responsive values without media queries. They choose the right value based on the available space.

- `min(a, b)`: picks the smaller value. Good for maximum widths.
- `max(a, b)`: picks the larger value. Good for minimum spacing.
- `clamp(min, ideal, max)`: ideal size that stays within the min and max bounds.

## Query / Code Blocks

```css
/* Responsive width: 90% of viewport, but never wider than 1200px */
.container {
    width: min(90%, 1200px);
    margin: 0 auto;
}

/* Minimum padding that grows on larger screens */
.section {
    padding: max(16px, 5vw);
}

/* Fluid typography: between 16px and 24px, scales with viewport */
h1 {
    font-size: clamp(1.5rem, 4vw, 3rem);
}

/* Card width: between 280px and 1fr, with a preferred 350px */
.card {
    width: clamp(280px, 50%, 400px);
}
```

## Performance / Optimization Notes

- `clamp()` replaces many typography media queries. One line handles all screen sizes.
- Use `min()` for containers to prevent overflow on small screens.
- These functions work in any property that accepts a numeric value: `width`, `font-size`, `padding`, `margin`.
