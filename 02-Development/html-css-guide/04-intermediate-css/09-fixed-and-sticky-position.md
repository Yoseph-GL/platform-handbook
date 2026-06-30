# CSS Intermediate: Fixed and Sticky Position

## Architecture / Rationale

`position: fixed` and `position: sticky` are two positioning values that make elements stay in place while the user scrolls.

- `fixed` — the element stays at the same position in the viewport. It is removed from the document flow.
- `sticky` — the element scrolls normally until it hits a threshold, then it sticks. It stays in the flow.

## Query / Code Blocks

```css
/* Fixed navbar: always visible at the top */
.navbar {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    background: white;
    padding: 16px;
    z-index: 100;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
}

/* Sticky section header: sticks when it reaches the top */
.section__header {
    position: sticky;
    top: 60px;  /* Leave space for the fixed navbar */
    background: #f5f5f5;
    padding: 8px 0;
    z-index: 10;
}
```

## Performance / Optimization Notes

- Fixed elements can cause scrolling performance issues on mobile. Use `will-change: transform` if needed.
- `sticky` only works inside a scrolling container. The parent must have enough height for scrolling.
- Always add a `top` value to `sticky` elements. Without it, the browser does not know when to stick.
