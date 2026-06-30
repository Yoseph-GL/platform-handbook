# CSS Intermediate: Object-fit and Object-position

## Architecture / Rationale

`object-fit` controls how an image or video fits inside its container. It is like `background-size` but for `<img>` and `<video>` elements.

`object-fit` values:
- `cover` — fills the container, cropping if needed. Keeps aspect ratio.
- `contain` — fits inside the container without cropping. May leave empty space.
- `fill` — stretches to fill the container. May distort the image.
- `none` — keeps the original size.

## Query / Code Blocks

```css
/* Image fills the container, cropped to fit */
.avatar {
    width: 150px;
    height: 150px;
    object-fit: cover;
    object-position: center;
    border-radius: 50%;
}

/* Image fits inside without cropping */
.product-image {
    width: 100%;
    height: 300px;
    object-fit: contain;
    object-position: center;
}

/* Focus on the top of the image */
.banner {
    width: 100%;
    height: 200px;
    object-fit: cover;
    object-position: top center;
}
```

## Performance / Optimization Notes

- `object-fit` is supported in all modern browsers, including IE11+.
- Use `object-position` to control which part of the image is visible when `cover` crops it.
- Set explicit `width` and `height` on the image. Without them, `object-fit` has no effect.
