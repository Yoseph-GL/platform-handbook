# CSS Responsive: Feature Queries

## Architecture / Rationale

Feature queries (`@supports`) let you apply CSS only when the browser supports a specific property. They are the modern way to handle browser differences.

- `@supports (property: value)` applies the rules if the browser understands the declaration.
- You can combine conditions with `and`, `or`, and `not`.
- Use them instead of browser-specific hacks or vendor prefixes.

## Query / Code Blocks

```css
/* Only apply Grid layout if the browser supports it */
@supports (display: grid) {
    .layout {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
    }
}

/* Fallback for browsers without Grid */
.layout {
    display: flex;
    flex-wrap: wrap;
}

/* Combine conditions */
@supports (display: grid) and (gap: 16px) {
    .layout {
        gap: 16px;
    }
}
```

## Performance / Optimization Notes

- Feature queries check a specific declaration, not the browser version. They work even on browsers you did not test.
- Put the fallback first and the enhanced layout inside `@supports`. The cascade makes the last rule win.
- Most modern CSS features (Grid, Flexbox, custom properties) are supported everywhere. Feature queries are useful for newer properties like `gap` in Flexbox.
