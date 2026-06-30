# CSS Flexbox: Order

## Architecture / Rationale

The `order` property changes the visual order of flex items without changing the HTML. All items start with `order: 0`. Lower numbers appear first, higher numbers appear last.

- The visual order is independent of the DOM order.
- Use `order` to reorder elements on different screen sizes (with media queries).
- Negative values are allowed: `order: -1` moves an item to the very front.

## Query / Code Blocks

```css
/* Default: all items have order: 0 */
.item {
    flex: 1;
}

/* Push this item to the end */
.item--last {
    order: 1;
}

/* Pull this item to the front */
.item--first {
    order: -1;
}
```

## Performance / Optimization Notes

- `order` changes the visual position but not the tab order. Keyboard users will tab through elements in the DOM order, which may differ from what they see.
- Test with a screen reader after using `order`. The reading order may not match what users expect.
- Use `order` sparingly. In most cases, rearranging the HTML gives a better result.
