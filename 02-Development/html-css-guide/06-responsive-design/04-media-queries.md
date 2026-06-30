# CSS Responsive: Media Queries

## Architecture / Rationale

Media queries apply CSS rules only when a condition is true. They are the main tool for adapting layouts to different screen sizes.

Syntax: `@media (condition) { /* CSS rules */ }`

Common conditions:
- `max-width`: applies up to a certain width.
- `min-width`: applies from a certain width upward.
- `prefers-color-scheme`: dark or light mode.
- `prefers-reduced-motion`: user prefers less animation.

## Query / Code Blocks

```css
/* Mobile styles (default, no media query) */
.card {
    width: 100%;
}

/* Tablet: 600px and wider */
@media (min-width: 600px) {
    .card {
        width: 50%;
    }
}

/* Desktop: 1024px and wider */
@media (min-width: 1024px) {
    .card {
        width: 33.33%;
    }
}

/* Dark mode */
@media (prefers-color-scheme: dark) {
    body {
        background: #1a1a1a;
        color: #f0f0f0;
    }
}
```

## Performance / Optimization Notes

- Write mobile styles first (outside media queries). Add complexity with `min-width` queries as the screen grows.
- Use 2-3 breakpoints, not 10. Common values: 600px, 900px, 1200px.
- Avoid `max-width` media queries in a mobile-first workflow. They lead to conflicting overrides.
