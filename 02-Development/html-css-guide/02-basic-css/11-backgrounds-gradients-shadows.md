# CSS Basics: Backgrounds, Gradients and Shadows

## Architecture / Rationale

Backgrounds and shadows add depth and visual interest to elements. CSS supports solid colors, images, gradients, and shadow effects.

- `background-color`: fills an element with a solid color.
- `background-image`: places an image or gradient behind the content.
- `box-shadow`: draws a shadow behind the element's box.
- `text-shadow`: draws a shadow behind text.

## Query / Code Blocks

```css
.hero {
    /* Solid background color */
    background-color: #2c3e50;

    /* Linear gradient (from top to bottom) */
    background-image: linear-gradient(to bottom, #3498db, #2980b9);

    /* Image with fallback color */
    background: #eee url('pattern.png') repeat center;

    /* Box shadow: x y blur color */
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.15);
}

.title {
    /* Text shadow: x y blur color */
    text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
}
```

## Performance / Optimization Notes

- Large `box-shadow` blur values can slow down scrolling. Keep blur radii under 50px for performance.
- Gradients are rendered by the browser and are faster than background images. Use them instead of images for simple color transitions.
- Combine multiple backgrounds on one element with commas: `background: url(a.png), url(b.png);`.
