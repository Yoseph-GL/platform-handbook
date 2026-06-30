# CSS Basics: Borders

## Architecture / Rationale

A border draws a line around an element. It sits between the padding and the margin. Borders can be solid, dashed, rounded, and have any color.

Border properties:
- `border-width`: thickness (in px or other units).
- `border-style`: solid, dashed, dotted, double, none.
- `border-color`: any color value.
- `border-radius`: rounds the corners.

## Query / Code Blocks

```css
.box {
    /* Shorthand: width style color */
    border: 2px solid #333;

    /* Individual sides */
    border-bottom: 3px dashed red;

    /* Rounded corners */
    border-radius: 8px;

    /* Circular element (width must equal height) */
    border-radius: 50%;
}
```

## Performance / Optimization Notes

- Use `border-radius` in small values (4-8px) for subtle rounded cards and buttons.
- Avoid thick borders that add to the element's calculated size unexpectedly.
- Borders are part of the box model. They affect layout unless `box-sizing: border-box` is set.
