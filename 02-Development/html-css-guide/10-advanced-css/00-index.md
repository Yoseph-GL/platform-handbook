# HTML/CSS Level 10: Advanced CSS

## Architecture / Rationale

This level covers modern CSS features that give you more power and flexibility. These properties let you write cleaner, more maintainable code.

Scope:
- Visual effects: filters and transforms.
- Responsive math: `min()`, `max()`, `clamp()`, `calc()`.
- Custom properties (CSS variables).
- Viewport units and intrinsic sizing keywords.
- Modern color functions.

## Query / Code Blocks

```html
<!-- Module pages -->
<!-- [[01-filter-and-backdrop-filter]] -->
<!-- [[02-transform]] -->
<!-- [[03-min-max-and-clamp]] -->
<!-- [[04-variables-custom-properties]] -->
<!-- [[05-calc-function]] -->
<!-- [[06-scroll-properties]] -->
<!-- [[07-initial-letter]] -->
<!-- [[08-viewport-units]] -->
<!-- [[09-min-max-fit-content]] -->
<!-- [[10-color-mix-function]] -->
```

## Performance / Optimization Notes

- Custom properties can be changed at runtime. They are more powerful than preprocessor variables.
- Use `clamp()` to replace media queries for typography and spacing.
- These features are modern CSS. Check browser support for the newest ones like `color-mix()`.
