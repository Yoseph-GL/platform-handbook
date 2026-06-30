# HTML Responsive: Picture, Source and Media

## Architecture / Rationale

The `<picture>` element gives you art direction. You can show completely different images at different screen sizes — not just different resolutions of the same image.

- `<picture>` wraps multiple `<source>` elements and one `<img>` fallback.
- Each `<source>` has a `media` condition. The first matching one is used.
- Use for: cropped images on mobile, different aspect ratios, or modern formats (WebP).

## Query / Code Blocks

```html
<picture>
    <!-- WebP format for modern browsers -->
    <source srcset="hero.webp" type="image/webp">

    <!-- Cropped version for small screens -->
    <source srcset="hero-mobile.jpg" media="(max-width: 600px)">

    <!-- Full version for larger screens -->
    <source srcset="hero-desktop.jpg" media="(min-width: 601px)">

    <!-- Fallback for old browsers -->
    <img src="hero-fallback.jpg" alt="Hero banner">
</picture>
```

## Performance / Optimization Notes

- Use `<picture>` for art direction (different crops). Use `srcset` for resolution switching (same image, different sizes).
- Put modern formats (WebP, AVIF) as the first `<source>`. Browsers that support them will load the smaller file.
- Always include an `<img>` fallback. Browsers that do not understand `<picture>` will display it.
