# CSS Grid: Introduction to Grid

## Architecture / Rationale

CSS Grid divides a container into rows and columns. You place items into the cells. It handles both dimensions together, unlike Flexbox which handles one at a time.

- Set `display: grid` on the parent to activate Grid.
- Define columns with `grid-template-columns` and rows with `grid-template-rows`.
- Items flow into the cells automatically, row by row.

## Query / Code Blocks

```css
.container {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-template-rows: auto;
    gap: 16px;
}

.item {
    background: #3498db;
    color: white;
    padding: 24px;
    text-align: center;
}
```

```html
<div class="container">
    <div class="item">1</div>
    <div class="item">2</div>
    <div class="item">3</div>
    <div class="item">4</div>
</div>
```

## Performance / Optimization Notes

- Grid is the right tool when you need to control rows and columns together (dashboards, page layouts, galleries).
- For a simple row of items, Flexbox is still fine. Grid is not a replacement for Flexbox — they complement each other.
- Use the browser DevTools Grid inspector to see the grid lines, gaps, and areas visually.
