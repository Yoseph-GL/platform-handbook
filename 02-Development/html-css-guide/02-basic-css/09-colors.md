# CSS Basics: Colors

## Architecture / Rationale

CSS supports many ways to define colors. Each format has its use case.

Color formats:
- **Named colors**: `red`, `blue`, `transparent`. Easy to read but limited.
- **Hex**: `#ff0000` (red), `#333` (dark gray). The most common format.
- **RGB/RGBA**: `rgb(255, 0, 0)`, `rgba(0, 0, 0, 0.5)`. The `a` sets opacity.
- **HSL**: `hsl(0, 100%, 50%)`. Intuitive for adjusting hue and saturation.

## Query / Code Blocks

```css
.text {
    color: #333;                     /* Hex */
    background-color: rgba(0,0,0,0.1); /* RGBA with opacity */
}

.button {
    background-color: hsl(210, 80%, 50%); /* HSL */
    color: white;
}

.card {
    border: 1px solid #e0e0e0;
    background-color: #fafafa;
}
```

## Performance / Optimization Notes

- Hex and RGB are the most compatible across all browsers.
- Use HSL when you need to programmatically adjust lightness or saturation.
- Maintain a color palette file with your brand colors as CSS custom properties. Do not scatter hex values across stylesheets.
