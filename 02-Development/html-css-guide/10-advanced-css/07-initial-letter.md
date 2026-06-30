# CSS Advanced: Initial Letter

## Architecture / Rationale

`initial-letter` creates a drop cap — a large first letter that spans multiple lines of text. It is a classic typographic technique for magazine and article layouts.

- `initial-letter: size sink` — size is the number of lines tall, sink is how far the letter drops.
- `initial-letter: 3` — a drop cap that is 3 lines tall.
- Only works on the first child inside a block container.

## Query / Code Blocks

```css
.article p:first-of-type::first-letter {
    initial-letter: 3;
    color: #3498db;
    font-weight: bold;
    margin-right: 8px;
}

/* Raised cap: stays above the text */
.raised-cap p:first-of-type::first-letter {
    initial-letter: 3 1;
    color: #e74c3c;
}

/* Accompanying styling */
.article p:first-of-type {
    font-size: 1.1rem;
    line-height: 1.7;
}
```

## Performance / Optimization Notes

- `initial-letter` is supported in Safari and Chrome. Firefox support is in development.
- Provide a fallback for unsupported browsers: style `::first-letter` with `font-size` and `float` separately.
- Only use drop caps on the first paragraph of an article. Multiple drop caps on one page look messy.
