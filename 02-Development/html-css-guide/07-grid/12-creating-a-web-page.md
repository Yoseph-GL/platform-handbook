# CSS Grid: Creating a Web Page

## Architecture / Rationale

This note combines all Grid properties to build a complete web page layout. It is the Grid equivalent of the Holy Grail exercise from Flexbox.

The page structure:
- Header with logo and navigation.
- Hero section with centered content.
- Three-column feature section.
- Footer with links and copyright.
- Responsive: stacks to one column on mobile.

## Query / Code Blocks

```css
.page {
    display: grid;
    grid-template-columns: 1fr min(1200px, 90%) 1fr;
}

.page > * {
    grid-column: 2;
}

.full-width {
    grid-column: 1 / -1;
}

/* Three-column features */
.features {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 32px;
}

/* Footer */
.footer {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 24px;
}

@media (max-width: 768px) {
    .footer {
        grid-template-columns: 1fr;
    }
}
```

## Performance / Optimization Notes

- The `.page > * { grid-column: 2; }` trick keeps content centered without a wrapper div on every section.
- Use `min(1200px, 90%)` as the center column width. On small screens, it uses 90% of the viewport. On large screens, it caps at 1200px.
- Full-width sections (hero, banners) use `grid-column: 1 / -1` to span edge to edge.
