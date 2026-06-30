# CSS Advanced: Viewport Units

## Architecture / Rationale

Viewport units size elements relative to the browser window. Modern CSS adds variants that account for mobile browser interfaces.

Viewport units:
- `vw` / `vh`: percentage of viewport width / height (100vw = full window width).
- `dvw` / `dvh`: dynamic viewport units. They adjust when mobile browser bars appear or disappear.
- `svw` / `svh`: small viewport units (with URL bar visible).
- `lvw` / `lvh`: large viewport units (with URL bar hidden).

## Query / Code Blocks

```css
/* Full-screen hero section */
.hero {
    height: 100vh;
    /* Problem: on mobile Safari, 100vh includes the space behind the URL bar.
       The bottom of the hero may be hidden. */
}

/* Better: dynamic viewport height */
.hero-dynamic {
    height: 100dvh;
    /* Adjusts when the URL bar shows or hides on mobile. */
}

/* Small viewport height (largest stable value) */
.section-stable {
    min-height: 100svh;
}

/* Fluid typography with viewport width */
.headline {
    font-size: clamp(2rem, 5vw, 4rem);
}
```

## Performance / Optimization Notes

- Use `dvh` instead of `vh` for full-screen sections on mobile. It prevents the URL bar from hiding content.
- `svh` is the safest unit for mobile. It represents the smallest possible viewport height.
- Viewport units are good for hero sections and fluid typography. Avoid using them for component-level sizing.
