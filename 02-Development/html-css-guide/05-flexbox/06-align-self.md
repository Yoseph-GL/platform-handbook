# CSS Flexbox: Align Self

## Architecture / Rationale

`align-self` overrides `align-items` for a single flex item. It lets one item align differently from its siblings on the cross axis.

- Uses the same values as `align-items`: `flex-start`, `flex-end`, `center`, `stretch`, `baseline`.
- Does not affect other items in the same container.

## Query / Code Blocks

```css
.container {
    display: flex;
    align-items: center; /* All items centered vertically */
    height: 200px;
    gap: 16px;
}

/* This item sticks to the top instead of being centered */
.item--top {
    align-self: flex-start;
}

/* This item stretches to the full height */
.item--tall {
    align-self: stretch;
}
```

## Performance / Optimization Notes

- Use `align-self: center` on a button inside a form row to center it vertically next to taller inputs.
- `align-self` is more maintainable than adding extra wrapper elements for alignment.
- Combine `align-self` with `margin: auto` on the cross axis for more layout flexibility.
