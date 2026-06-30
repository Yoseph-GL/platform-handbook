# CSS Intermediate: Display

## Architecture / Rationale

The `display` property is one of the most important CSS properties. It determines how an element behaves in the layout flow.

Common display values:
- `block` — takes full width, creates a new line. Example: `<div>`, `<p>`.
- `inline` — takes only needed width, stays in the text flow. Example: `<span>`, `<a>`.
- `inline-block` — like inline but respects width and height.
- `none` — removes the element from the layout entirely.

## Query / Code Blocks

```css
.block-element {
    display: block;
    width: 100%;
}

.inline-element {
    display: inline;
    /* width and height have no effect */
}

.inline-block-element {
    display: inline-block;
    width: 200px;
    height: 100px;
}

.hidden-element {
    display: none;
    /* Element is removed from layout. Space collapses. */
}

.invisible-element {
    visibility: hidden;
    /* Element is invisible but still takes up space. */
}
```

## Performance / Optimization Notes

- `display: none` removes the element from the layout flow. Other elements fill its space.
- Use `visibility: hidden` when you want to hide something but keep its layout space.
- Changing `display` on hover can cause layout shifts. Use `opacity` or `visibility` for smooth effects instead.
