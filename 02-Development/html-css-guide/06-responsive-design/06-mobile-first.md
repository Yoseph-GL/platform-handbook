# CSS Responsive: Mobile First

## Architecture / Rationale

Mobile-first means you design and write CSS for small screens first, then add complexity for larger screens. It is the opposite of the old desktop-first approach.

Why mobile-first:
- Small screens have less space. You must prioritize what really matters.
- CSS without media queries is the mobile layout. `min-width` queries add layout for tablets and desktops.
- Mobile devices are more limited in CPU and bandwidth. Starting simple keeps them fast.

## Query / Code Blocks

```css
/* Base: mobile styles (no media query) */
.card-list {
    display: flex;
    flex-direction: column;
    gap: 16px;
}

/* Tablet: 600px+ */
@media (min-width: 600px) {
    .card-list {
        flex-direction: row;
        flex-wrap: wrap;
    }
    .card {
        flex: 1 1 280px;
    }
}

/* Desktop: 1024px+ */
@media (min-width: 1024px) {
    .card-list {
        max-width: 1200px;
        margin: 0 auto;
    }
}
```

## Performance / Optimization Notes

- Mobile-first CSS loads faster on mobile because browsers apply fewer overrides.
- Use `min-width`, not `max-width`, for media queries in a mobile-first workflow.
- Test without CSS first. If the HTML content is clear and logical as plain text, the layout is on the right track.
