# CSS Grid: Auto and FR Units

## Architecture / Rationale

`auto` and `fr` are the two flexible sizing units in CSS Grid. They behave differently and have different use cases.

- `fr` (fraction): takes a share of the available space. `1fr 2fr` means one third and two thirds.
- `auto`: sizes to the content. The track grows or shrinks to fit its items.
- Mix `auto` and `fr`: `auto` columns fit content, `fr` columns fill remaining space.

## Query / Code Blocks

```css
/* fr units: proportional distribution */
.grid-fr {
    display: grid;
    grid-template-columns: 1fr 2fr 1fr;
    /* Total: 4 fractions. Middle column gets half the space. */
}

/* auto: fits content size */
.grid-auto {
    display: grid;
    grid-template-columns: auto 1fr auto;
    /* Left and right columns fit their content. Center fills the rest. */
}

/* Fixed + fr + auto */
.grid-mixed {
    display: grid;
    grid-template-columns: 200px 1fr auto;
}
```

## Performance / Optimization Notes

- `fr` only distributes free space. Content that is wider than the fraction can push the column bigger.
- Use `auto` for tracks that should match their content (like an icon column or a label).
- `fr` is similar to `flex-grow` in Flexbox. It is the core of flexible Grid layouts.
