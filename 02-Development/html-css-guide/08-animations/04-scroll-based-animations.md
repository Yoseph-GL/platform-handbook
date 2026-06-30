# CSS Animations: Scroll-based Animations

## Architecture / Rationale

Scroll-based animations trigger as the user scrolls. Elements can fade in, slide up, or change based on scroll position. Modern CSS supports this natively.

- `animation-timeline: scroll()` links the animation progress to the scroll position.
- Elements animate as they enter the viewport, without JavaScript.
- These animations are declarative and performant.

## Query / Code Blocks

```css
@keyframes appear {
    from {
        opacity: 0;
        transform: translateY(40px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}

/* Animate when the element scrolls into view */
.reveal {
    animation: appear 0.8s ease-out;
    animation-timeline: view();
    animation-range: entry 0% entry 100%;
}

/* Animate based on scroll position of the page */
.parallax {
    animation: parallax-shift linear;
    animation-timeline: scroll();
}

@keyframes parallax-shift {
    from { transform: translateY(0); }
    to   { transform: translateY(-200px); }
}
```

## Performance / Optimization Notes

- Scroll-based animations are still new. Check browser support before relying on them in production.
- Fallback: show all content without animations for browsers that do not support `animation-timeline`.
- These animations run on the compositor thread. They do not block the main thread.
