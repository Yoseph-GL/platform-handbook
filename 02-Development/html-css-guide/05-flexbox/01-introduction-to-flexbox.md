# CSS Flexbox: Introduction to Flexbox

## Architecture / Rationale

Flexbox turns a container into a flex container. Its direct children become flex items and line up in a row or column. You control their size, spacing, and alignment with simple properties.

- Set `display: flex` on the parent to activate Flexbox.
- The main axis runs in the flex direction (default: left to right).
- The cross axis runs perpendicular to the main axis.

## Query / Code Blocks

```css
/* Simple flex container */
.container {
    display: flex;
    gap: 16px;
}

/* Items automatically sit in a row */
.item {
    padding: 16px;
    background: #3498db;
    color: white;
}
```

```html
<div class="container">
    <div class="item">Item 1</div>
    <div class="item">Item 2</div>
    <div class="item">Item 3</div>
</div>
```

## Performance / Optimization Notes

- Flexbox is on by default in all modern codebases. It replaces float and inline-block hacks.
- The `gap` property replaces unreliable margin tricks for spacing items.
- Use Flexbox for navigation bars, card lists, and centering content vertically.
