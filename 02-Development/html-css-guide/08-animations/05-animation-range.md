# CSS Animations: Animation Range

## Architecture / Rationale

`animation-range` controls when a scroll-based animation starts and ends. It lets you fine-tune exactly where in the scroll timeline the animation plays.

- `animation-range: entry` — the animation plays while the element enters the viewport.
- `animation-range: exit` — plays while the element exits.
- `animation-range: contain` — plays while the element is fully inside the viewport.
- Custom ranges: `entry 25%` to `exit 75%`.

## Query / Code Blocks

```css
/* Start animating when 25% of the element is visible,
   finish when 80% of the element has entered */
.card {
    animation: slide-in 1s ease-out;
    animation-timeline: view();
    animation-range: entry 25% entry 80%;
}

/* Animate across the entire visible scroll range */
.hero-title {
    animation: fade-scale linear;
    animation-timeline: view();
    animation-range: cover 0% cover 100%;
}

@keyframes slide-in {
    from { opacity: 0; transform: translateX(-60px); }
    to   { opacity: 1; transform: translateX(0); }
}

@keyframes fade-scale {
    from { opacity: 0.3; transform: scale(0.8); }
    to   { opacity: 1; transform: scale(1); }
}
```

## Performance / Optimization Notes

- Test animation ranges on multiple devices. Scroll distances vary between desktop and mobile.
- Shorter ranges (10-20% of the scroll) create snappier animations. Longer ranges feel gradual.
- Use `cover` for elements that should animate across the full visible scroll of the viewport.
