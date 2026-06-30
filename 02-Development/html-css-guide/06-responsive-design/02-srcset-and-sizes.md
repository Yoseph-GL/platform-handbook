# HTML Responsive: SRCSET and SIZES Attributes

## Architecture / Rationale

`srcset` and `sizes` let the browser choose the best image file for the user's screen. Small screens get small images. Large screens get high-resolution images.

- `srcset`: a list of image files with their widths (`image-480.jpg 480w`).
- `sizes`: tells the browser how wide the image will be at different screen sizes.
- The browser picks the optimal file, saving bandwidth on mobile.

## Query / Code Blocks

```html
<!-- Simple resolution switching -->
<img src="photo-800.jpg"
     srcset="photo-400.jpg 400w,
             photo-800.jpg 800w,
             photo-1200.jpg 1200w"
     sizes="(max-width: 600px) 100vw,
            (max-width: 1200px) 50vw,
            33vw"
     alt="A landscape photo">
```

## Performance / Optimization Notes

- Always include a `src` fallback for browsers that do not support `srcset`.
- Generate images in 3-4 sizes (400w, 800w, 1200w, 1800w). More than that adds complexity without much benefit.
- Use a build tool or image CDN to generate multiple sizes automatically. Do not create them by hand.
