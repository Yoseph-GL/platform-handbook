# CSS Intermediate: Overflow

## Architecture / Rationale

`overflow` controls what happens when content is larger than its container. You can clip it, show scrollbars, or let it spill out.

Overflow values:
- `visible` (default) — content spills out of the container.
- `hidden` — content is clipped. No scrollbars.
- `scroll` — scrollbars always visible.
- `auto` — scrollbars appear only when needed.

## Query / Code Blocks

```css
/* Scroll when content overflows */
.code-block {
    max-height: 300px;
    overflow-y: auto;
    background: #1e1e1e;
    color: #d4d4d4;
    padding: 16px;
    border-radius: 4px;
}

/* Clip text with ellipsis */
.ellipsis {
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
}

/* Image that fits inside a container */
.image-wrapper {
    width: 300px;
    height: 200px;
    overflow: hidden;
    border-radius: 8px;
}
```

## Performance / Optimization Notes

- `overflow: hidden` on the body can prevent unwanted horizontal scrollbars from fixed-width elements.
- `text-overflow: ellipsis` only works with `white-space: nowrap` and `overflow: hidden` on the same element.
- Scrollable containers should have a visible focus style. Keyboard users need to know which element is focused.
