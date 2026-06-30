# CSS Intermediate: Selectors (Advanced)

## Architecture / Rationale

Advanced selectors let you target elements based on attributes, relationships, and patterns. They make your CSS more powerful and reduce the need for extra classes.

Selector types:
- **Attribute selectors**: `[type]`, `[href^="https"]`, `[class~="card"]`.
- **Combinators**: child (`>`), adjacent sibling (`+`), general sibling (`~`).
- **Multiple classes**: chain selectors like `.card.featured`.

## Query / Code Blocks

```css
/* Attribute selector: all inputs of type text */
input[type="text"] {
    border: 1px solid #ccc;
}

/* Starts with: links that begin with https */
a[href^="https"] {
    color: green;
}

/* Child combinator: direct children only */
nav > ul > li {
    display: inline-block;
}

/* Adjacent sibling: paragraph right after an h2 */
h2 + p {
    margin-top: 0;
}

/* General sibling: all paragraphs after an h2 */
h2 ~ p {
    color: #555;
}
```

## Performance / Optimization Notes

- Attribute selectors are slower than class selectors. Use classes for frequently-matched elements.
- The child combinator (`>`) is more efficient than the descendant combinator (space) because the browser stops searching after the direct child.
- Avoid selector chains longer than 3 levels. They are hard to read and slow to match.
