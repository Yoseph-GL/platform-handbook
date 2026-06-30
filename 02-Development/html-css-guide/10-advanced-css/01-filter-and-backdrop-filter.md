# CSS Advanced: Filter and Backdrop Filter

## Architecture / Rationale

CSS filters apply visual effects to elements. `filter` affects the element itself. `backdrop-filter` affects the area behind the element.

Common filter functions:
- `blur()` — gaussian blur.
- `brightness()` — lighten or darken.
- `contrast()` — increase or decrease contrast.
- `grayscale()` — make black and white.
- `saturate()` — boost or reduce color.

## Query / Code Blocks

```css
/* Blur an image */
.blurred {
    filter: blur(5px);
}

/* Multiple filters combined */
.image-effect {
    filter: grayscale(80%) brightness(1.1) contrast(1.2);
}

/* Frosted glass effect */
.glass-card {
    background: rgba(255, 255, 255, 0.2);
    backdrop-filter: blur(10px);
    border: 1px solid rgba(255, 255, 255, 0.3);
}

/* Hover: remove filter */
img:hover {
    filter: none;
}
```

## Performance / Optimization Notes

- `backdrop-filter` can be GPU-intensive. Test on mobile before using it on large areas.
- Combine `filter` with `transition` for smooth hover effects.
- Heavy `blur()` values (over 20px) can cause rendering lag on low-end devices.
