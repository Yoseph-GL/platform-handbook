# CSS Flexbox: Flex Basis, Shrink and Grow

## Architecture / Rationale

The `flex` shorthand controls how items size themselves and share extra space. It is one of the most powerful concepts in Flexbox.

Three components:
- `flex-basis`: the starting size of the item before growing or shrinking.
- `flex-grow`: how much the item grows if there is extra space (proportion).
- `flex-shrink`: how much the item shrinks if there is not enough space.

## Query / Code Blocks

```css
.item {
    /* flex: grow shrink basis */
    flex: 1 1 300px;
    /* flex-grow: 1, flex-shrink: 1, flex-basis: 300px */
}

/* Fixed-size item: cannot grow or shrink */
.item--fixed {
    flex: 0 0 200px;
}

/* Item that takes all available space */
.item--stretch {
    flex: 1 1 auto;
}

/* Common shorthand values */
flex: 1;       /* 1 1 0% — grow equally */
flex: auto;    /* 1 1 auto — grow based on content */
flex: none;    /* 0 0 auto — stay fixed */
```

## Performance / Optimization Notes

- `flex: 1` on all items makes them equal width. This is much cleaner than fixed pixel widths.
- `flex-shrink: 0` prevents an item from compressing when there is not enough room. Useful for icons and badges.
- The `flex` shorthand is preferred over writing `flex-grow`, `flex-shrink`, and `flex-basis` separately.
