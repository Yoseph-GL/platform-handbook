# CSS Basics: Units

## Architecture / Rationale

CSS units define sizes, spacing, and positions. Choosing the right unit makes layouts flexible and responsive.

Unit categories:
- **Absolute**: `px` (pixels). Fixed size, always the same.
- **Relative to font**: `em` (parent's font size), `rem` (root font size).
- **Relative to viewport**: `vw` (viewport width), `vh` (viewport height).
- **Percentage**: `%` relative to the parent element's size.

## Query / Code Blocks

```css
html {
    font-size: 16px; /* 1rem = 16px */
}

.text {
    font-size: 1rem;       /* 16px, relative to root */
    margin-bottom: 1.5em;  /* 1.5 × current font size */
    max-width: 800px;      /* Fixed pixel width */
    width: 90%;            /* 90% of parent container */
}

.hero {
    height: 50vh;  /* 50% of viewport height */
}
```

## Performance / Optimization Notes

- Use `rem` for font sizes and spacing. It scales with the user's browser settings.
- Use `px` for small details like borders and box shadows.
- Use `%` or viewport units for layout widths. Absolute widths cause horizontal scrolling on small screens.
