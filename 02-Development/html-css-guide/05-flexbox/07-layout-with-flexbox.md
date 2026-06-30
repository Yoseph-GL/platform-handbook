# CSS Flexbox: Layout with Flexbox

## Architecture / Rationale

This note combines all Flexbox properties into real-world layout patterns. You use these patterns every day in front-end work.

Common patterns:
- **Navbar**: logo on the left, links on the right (`space-between`).
- **Card grid**: cards that wrap to the next row (`flex-wrap: wrap`).
- **Centered content**: one element perfectly centered (`justify-content` + `align-items: center`).
- **Sticky footer**: push the footer to the bottom (`flex: 1` on the main content).

## Query / Code Blocks

```css
/* Navbar pattern */
.navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 16px 24px;
}

/* Card grid pattern */
.card-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 24px;
}
.card {
    flex: 1 1 300px;
}

/* Centered content pattern */
.hero {
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 80vh;
}

/* Sticky footer pattern */
.page {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
}
.page__content {
    flex: 1;
}
```

## Performance / Optimization Notes

- These four patterns solve roughly 80% of layout tasks. Master them before moving to Grid.
- Use `gap` instead of margin for spacing between flex items. It is simpler and always correct at the edges.
- Test flex layouts on small screens. Wrap behaviors can look different on mobile.
