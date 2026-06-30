# CSS Advanced: Scroll Properties

## Architecture / Rationale

Modern CSS gives you control over how elements scroll. These properties improve user experience in scrollable containers.

- `scroll-behavior: smooth` — smooth scrolling when clicking anchor links.
- `scroll-snap-type` and `scroll-snap-align` — snap scrolling (like a carousel or slideshow).
- `scroll-padding` — offset for scroll targets (avoids hiding content under a fixed header).
- `overscroll-behavior` — prevents scroll chaining (the background scrolling when a modal is open).

## Query / Code Blocks

```css
/* Smooth scrolling for the whole page */
html {
    scroll-behavior: smooth;
}

/* Offset for fixed header when jumping to sections */
html {
    scroll-padding-top: 80px;
}

/* Snap scrolling gallery */
.gallery {
    display: flex;
    overflow-x: auto;
    scroll-snap-type: x mandatory;
}
.gallery__item {
    scroll-snap-align: start;
    flex: 0 0 100%;
}

/* Prevent background scroll when modal is open */
.modal-open {
    overscroll-behavior: contain;
    overflow: hidden;
}
```

## Performance / Optimization Notes

- `scroll-behavior: smooth` works for anchor links (`#section`) without JavaScript.
- `scroll-snap-type` is supported everywhere. It is the standard way to build carousels.
- Always pair `scroll-padding-top` with a fixed header. Without it, section titles hide behind the navbar.
