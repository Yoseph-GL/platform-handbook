# HTML Basics: Images and Paths

## Architecture / Rationale

Images make web pages visual and engaging. The `<img>` tag embeds an image into the page. It is a self-closing tag.

Image rules:
- `src` tells the browser where the image file is (the path).
- `alt` provides a text description for screen readers and when the image fails to load.
- File paths can be relative (`images/photo.jpg`) or absolute (`https://example.com/photo.jpg`).

## Query / Code Blocks

```html
<!-- Basic image with alt text -->
<img src="images/photo.jpg" alt="A sunset over the ocean">

<!-- Image with width and height attributes (reserves space while loading) -->
<img src="logo.png" alt="Company logo" width="200" height="100">

<!-- Image from an external URL -->
<img src="https://example.com/banner.jpg" alt="Promotional banner">
```

## Performance / Optimization Notes

- Always include the `alt` attribute. It is required for accessibility.
- Use the `width` and `height` attributes to prevent layout shifts while images load.
- Compress images before uploading. Large image files are the most common cause of slow pages.
- Use modern formats like WebP for smaller file sizes.
