# HTML/CSS Level 7: CSS Grid

## Architecture / Rationale

CSS Grid is a two-dimensional layout system. It controls both rows and columns at the same time. Grid is the most powerful layout tool in CSS.

Scope:
- Grid containers, items, tracks, and gaps.
- `auto` and `fr` units for flexible sizing.
- Repeat, minmax, and dynamic grids.
- Implicit vs explicit grid placement.
- Grid areas and named templates.
- Alignment and subgrid.

## Query / Code Blocks

```html
<!-- Module pages -->
<!-- [[01-introduction-to-grid]] -->
<!-- [[02-creating-a-grid]] -->
<!-- [[03-auto-and-fr-units]] -->
<!-- [[04-repeat-and-minmax]] -->
<!-- [[05-implicit-and-explicit-grid]] -->
<!-- [[06-dynamic-grid]] -->
<!-- [[07-grid-column-and-grid-row]] -->
<!-- [[08-grid-flow-dense]] -->
<!-- [[09-grid-areas]] -->
<!-- [[10-alignment-with-grid]] -->
<!-- [[11-subgrid]] -->
<!-- [[12-creating-a-web-page]] -->
```

## Performance / Optimization Notes

- Use Grid for two-dimensional layouts (rows AND columns). Use Flexbox for one-dimensional layouts.
- Grid is supported everywhere. No feature query needed for basic usage.
- Complex Grid templates are easier to read than deeply nested Flexbox containers.
