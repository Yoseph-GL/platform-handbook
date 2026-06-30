# CSS Animations: Integrating Animations in a Web

## Architecture / Rationale

Animations must feel like part of the design, not an afterthought. This note covers how to add animations that enhance your site without overwhelming it.

Guidelines for integration:
- Animate one element at a time. Too many moving parts confuse the user.
- Use the same easing function across related animations for cohesion.
- Animation tells a story: elements appear in a logical order (top to bottom, hero first).

## Query / Code Blocks

```css
/* Staggered entrance for a list */
.list-item {
    opacity: 0;
    animation: fade-in 0.5s ease forwards;
}
.list-item:nth-child(1) { animation-delay: 0.1s; }
.list-item:nth-child(2) { animation-delay: 0.2s; }
.list-item:nth-child(3) { animation-delay: 0.3s; }
.list-item:nth-child(4) { animation-delay: 0.4s; }
.list-item:nth-child(5) { animation-delay: 0.5s; }

/* Disable animations for users who prefer reduced motion */
@media (prefers-reduced-motion: reduce) {
    *,
    *::before,
    *::after {
        animation-duration: 0.01ms !important;
        transition-duration: 0.01ms !important;
    }
}
```

## Performance / Optimization Notes

- Always include a `prefers-reduced-motion` media query. It is an accessibility requirement, not optional.
- Stagger animations by at most 100-150ms per item. Longer delays feel sluggish.
- Keep entrance animations under 600ms. Anything longer makes the page feel slow to load.
