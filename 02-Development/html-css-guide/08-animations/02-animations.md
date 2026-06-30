# CSS Animations: Animations

## Architecture / Rationale

CSS animations go beyond transitions. They can run automatically, loop, and have multiple steps. You define them with `@keyframes` and apply them with the `animation` property.

- `@keyframes name` defines percentage-based steps (0% → 100%, or `from` → `to`).
- `animation-name` links the element to the keyframes.
- Control with `animation-duration`, `animation-iteration-count`, `animation-direction`, and `animation-fill-mode`.

## Query / Code Blocks

```css
@keyframes fade-in {
    from {
        opacity: 0;
        transform: translateY(20px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}

@keyframes pulse {
    0%, 100% { transform: scale(1); }
    50%      { transform: scale(1.05); }
}

.element {
    animation: fade-in 0.5s ease-out;
}

.looping {
    animation: pulse 2s ease-in-out infinite;
}

/* Shorthand: name duration timing-function delay count direction fill-mode */
.banner {
    animation: fade-in 1s ease 0.5s 1 normal forwards;
}
```

## Performance / Optimization Notes

- `animation-fill-mode: forwards` keeps the element at the final keyframe state after the animation ends.
- Use `animation-delay` to stagger multiple elements appearing in sequence.
- Test animations on a low-end phone. What looks smooth on desktop may stutter on mobile.
