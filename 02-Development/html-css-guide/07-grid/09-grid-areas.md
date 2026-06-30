# CSS Grid: Grid Areas

## Architecture / Rationale

`grid-template-areas` lets you name parts of your layout and assign items to them. It is the most readable way to create page layouts with Grid.

- Define areas with a text grid in `grid-template-areas`. Each word names an area.
- Assign items to areas with `grid-area: name;`.
- The visual layout is visible right in the CSS code.

## Query / Code Blocks

```css
.page {
    display: grid;
    grid-template-columns: 200px 1fr 200px;
    grid-template-rows: auto 1fr auto;
    grid-template-areas:
        "header  header  header"
        "sidebar main    aside"
        "footer  footer  footer";
    min-height: 100vh;
    gap: 16px;
}

.header  { grid-area: header; }
.sidebar { grid-area: sidebar; }
.main    { grid-area: main; }
.aside   { grid-area: aside; }
.footer  { grid-area: footer; }

/* Responsive: stack everything on mobile */
@media (max-width: 768px) {
    .page {
        grid-template-columns: 1fr;
        grid-template-areas:
            "header"
            "main"
            "sidebar"
            "aside"
            "footer";
    }
}
```

## Performance / Optimization Notes

- Grid areas make the layout readable at a glance. Use them for the main page skeleton.
- Changing the layout for mobile is as simple as redefining `grid-template-areas`.
- Every area must form a rectangle. L-shaped areas are not possible with `grid-template-areas`.
