# CSS Responsive: Flexible Blocks and Multimedia

## Architecture / Rationale

Flexible blocks and multimedia scale with the container. Instead of fixed pixel widths, they use percentages, `max-width`, and responsive units.

Key techniques:
- Use `max-width: 100%` on images so they never overflow their container.
- Use percentage widths for layout columns.
- Use `aspect-ratio` to keep video proportions at any width.

## Query / Code Blocks

```css
/* Images that never overflow */
img, video {
    max-width: 100%;
    height: auto;
}

/* Flexible column layout */
.column {
    width: 50%;
    float: left;
}

/* Keep video aspect ratio */
.video-container {
    aspect-ratio: 16 / 9;
}
.video-container iframe {
    width: 100%;
    height: 100%;
}
```

## Performance / Optimization Notes

- `max-width: 100%` on all images is a quick win for responsive layouts. Add it to your reset styles.
- Avoid fixed pixel widths on layout elements. Use `%`, `fr`, or `rem` instead.
- Test images at 320px wide. If they look wrong, your responsive image strategy needs work.
