# HTML Advanced: Lazy Loading

## Architecture / Rationale

Lazy loading delays loading images and other resources until the user scrolls near them. It makes the first page load much faster.

- `loading="lazy"` on `<img>` tells the browser to load the image only when it is about to appear on screen.
- `loading="eager"` (the default) loads the image immediately.
- Use lazy loading for images below the fold (not visible on first load).

## Query / Code Blocks

```html
<!-- Image above the fold: load immediately -->
<img src="hero.jpg" alt="Hero banner" loading="eager">

<!-- Images below the fold: load when needed -->
<img src="gallery-1.jpg" alt="Gallery photo 1" loading="lazy">
<img src="gallery-2.jpg" alt="Gallery photo 2" loading="lazy">
<img src="gallery-3.jpg" alt="Gallery photo 3" loading="lazy">

<!-- Lazy loading also works on iframes -->
<iframe src="https://example.com/map" loading="lazy" width="600" height="400">
</iframe>
```

## Performance / Optimization Notes

- Lazy loading is built into modern browsers. You do not need JavaScript for basic cases.
- Always set `width` and `height` on lazy-loaded images to prevent layout shift.
- Never lazy-load the main hero image at the top of the page. It must appear immediately.
