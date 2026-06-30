# CSS Advanced: Color Mix Function

## Architecture / Rationale

`color-mix()` lets you blend two colors in CSS without a preprocessor or JavaScript. It is a native way to create tints, shades, and variations of your brand colors.

- `color-mix(in <colorspace>, <color1> <percentage>, <color2> <percentage>)`
- Common color spaces: `srgb`, `oklch`, `hsl`.
- Create hover states, backgrounds, and accent colors from a single base color.

## Query / Code Blocks

```css
:root {
    --brand: #3498db;
}

/* Lighten the brand color: mix with white */
.button {
    background-color: var(--brand);
}
.button:hover {
    background-color: color-mix(in srgb, var(--brand) 80%, white 20%);
}

/* Darken the brand color: mix with black */
.header {
    background-color: color-mix(in srgb, var(--brand) 70%, black 30%);
}

/* Semi-transparent version of the brand color */
.overlay {
    background-color: color-mix(in srgb, var(--brand) 50%, transparent 50%);
}

/* Using oklch for perceptually uniform mixing */
.card {
    background-color: color-mix(in oklch, var(--brand) 90%, white 10%);
}
```

## Performance / Optimization Notes

- `color-mix()` eliminates the need for color manipulation libraries in many cases.
- Use `oklch` color space for more natural-looking color mixtures. `srgb` can produce muddy results.
- Check browser support. `color-mix()` is available in Chrome 111+, Safari 16.2+, and Firefox 113+.
