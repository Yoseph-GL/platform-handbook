# CSS Responsive: Holy Grail with Flexbox

## Architecture / Rationale

The Holy Grail layout is a classic web layout: header, footer, main content, and two sidebars. Flexbox makes it clean and responsive without hacks.

The pattern:
- A column flex container for the page (header, content area, footer).
- A row flex container for the content area (sidebar, main, sidebar).
- On small screens, the sidebars stack below the main content.

## Query / Code Blocks

```css
.page {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
}

.content {
    display: flex;
    flex: 1;
}

.main {
    flex: 1;
    padding: 24px;
}

.sidebar {
    width: 250px;
    padding: 24px;
}

.sidebar--left {
    order: -1;
}

/* Stack on mobile */
@media (max-width: 768px) {
    .content {
        flex-direction: column;
    }
    .sidebar {
        width: 100%;
    }
}
```

## Performance / Optimization Notes

- The Holy Grail is the base for most web applications: blogs, dashboards, stores.
- Use `order` to control the visual position of sidebars without changing the HTML.
- The layout above uses no floats or absolute positioning. Everything stays in flow.
