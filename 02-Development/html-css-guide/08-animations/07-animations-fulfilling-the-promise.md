# CSS Animations: Fulfilling the Promise

## Architecture / Rationale

This note brings together everything from the animations module. The "promise" of CSS animations is that you can create rich, interactive experiences without JavaScript.

Summary of what you can do with pure CSS:
- Hover effects and button feedback (transitions).
- Looping animations like spinners and loaders (keyframes).
- Entrance animations (keyframes with delay).
- Scroll-driven storytelling (animation-timeline).

## Query / Code Blocks

```css
/* A complete, production-ready animation setup */

/* 1. Respect user preferences */
@media (prefers-reduced-motion: reduce) {
    *, *::before, *::after {
        animation-duration: 0.01ms !important;
        transition-duration: 0.01ms !important;
    }
}

/* 2. Define your keyframes once, reuse them */
@keyframes fade-up {
    from { opacity: 0; transform: translateY(30px); }
    to   { opacity: 1; transform: translateY(0); }
}

/* 3. Apply with consistent timing */
.animate-in {
    animation: fade-up 0.5s ease-out forwards;
}

/* 4. Use a utility for staggered children */
.stagger > * {
    opacity: 0;
    animation: fade-up 0.5s ease-out forwards;
}
.stagger > *:nth-child(1) { animation-delay: 0.1s; }
.stagger > *:nth-child(2) { animation-delay: 0.2s; }
.stagger > *:nth-child(3) { animation-delay: 0.3s; }
```

## Performance / Optimization Notes

- CSS animations are not a replacement for JavaScript interaction. They work together: CSS for visual transitions, JavaScript for logic and state.
- Profile your animations in DevTools. Look for dropped frames and long paint times.
- Good animation is invisible. If users notice the animation before the content, tone it down.
