# CSS Intermediate: Relative and Absolute Positioning

## Architecture / Rationale

Positioning lets you move elements from their normal flow position. `relative` and `absolute` are the most useful values.

- `position: relative` — the element stays in the flow but you can offset it with `top`/`right`/`bottom`/`left`. It also creates a positioning context for children.
- `position: absolute` — the element is removed from the flow and positioned relative to the nearest positioned ancestor (or the page).

## Query / Code Blocks

```css
/* Parent: creates a positioning context */
.card {
    position: relative;
    padding: 24px;
}

/* Child: positioned relative to .card */
.card__badge {
    position: absolute;
    top: -10px;
    right: -10px;
    background: red;
    color: white;
    padding: 4px 8px;
    border-radius: 50%;
}

/* Slight offset from normal position */
.shifted {
    position: relative;
    top: 4px;
    left: 4px;
}
```

## Performance / Optimization Notes

- The parent of an absolute element must have `position: relative` (or `absolute`/`fixed`). Otherwise, the element positions itself against the whole page.
- Absolute elements are removed from the flow. Siblings act like the element does not exist.
- Use relative positioning for small adjustments. Prefer margin or transform for larger layout shifts.
