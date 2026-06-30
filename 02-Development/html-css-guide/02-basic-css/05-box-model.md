# CSS Basics: Box Model

## Architecture / Rationale

Every HTML element is a rectangular box. The CSS box model defines the parts of that box and how they affect layout.

The four layers (from inside to outside):
- **Content**: the text or image inside the element.
- **Padding**: space between the content and the border.
- **Border**: a line around the padding (and content).
- **Margin**: space between the border and other elements.

## Query / Code Blocks

```css
.box {
    width: 300px;
    padding: 20px;
    border: 2px solid black;
    margin: 30px;
}

/* The total width of the box:
   width (300) + padding (20+20) + border (2+2) = 344px (with default box-sizing) */
```

## Performance / Optimization Notes

- Understand that padding and border add to the element's size by default. Use `box-sizing: border-box` to include them in the width.
- Use the browser's DevTools to inspect the box model of any element. It shows all four layers.
- Avoid setting large fixed margins on reusable components. Use spacing utilities or a consistent scale instead.
