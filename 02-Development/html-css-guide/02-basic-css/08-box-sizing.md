# CSS Basics: Box Sizing

## Architecture / Rationale

`box-sizing` changes how the browser calculates an element's width and height. It is one of the most important CSS properties to understand early.

Two values:
- `content-box` (default): `width` means the content area only. Padding and border add extra size.
- `border-box`: `width` includes content, padding, and border. The total size is what you set.

## Query / Code Blocks

```css
/* Apply border-box to everything — a common reset */
*,
*::before,
*::after {
    box-sizing: border-box;
}

/* Without border-box: total width = 300 + 40 + 4 = 344px */
.card-content {
    width: 300px;
    padding: 20px;
    border: 2px solid black;
    box-sizing: content-box;
}

/* With border-box: total width = 300px (content shrinks to fit) */
.card-border {
    width: 300px;
    padding: 20px;
    border: 2px solid black;
    box-sizing: border-box;
}
```

## Performance / Optimization Notes

- Set `box-sizing: border-box` globally at the top of every project. It makes layout math predictable.
- Without border-box, a `width: 100%` plus padding causes horizontal scrollbars.
- This rule has no performance cost. Apply it and forget about it.
