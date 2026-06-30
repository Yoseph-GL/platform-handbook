# CSS Intermediate: Transitions

## Architecture / Rationale

A transition smoothly changes a CSS property from one value to another. It makes hover effects, color changes, and size animations feel smooth.

Transition properties:
- `transition-property`: which property to animate.
- `transition-duration`: how long the animation takes.
- `transition-timing-function`: the acceleration curve (ease, linear, ease-in-out).
- `transition-delay`: wait time before starting.

## Query / Code Blocks

```css
.button {
    background-color: #3498db;
    color: white;
    padding: 12px 24px;
    border: none;
    border-radius: 4px;
    transition: background-color 0.3s ease, transform 0.2s ease;
}

.button:hover {
    background-color: #2980b9;
    transform: translateY(-2px);
}

.card {
    transition: box-shadow 0.3s ease, transform 0.3s ease;
}

.card:hover {
    box-shadow: 0 8px 24px rgba(0, 0, 0, 0.15);
    transform: scale(1.02);
}
```

## Performance / Optimization Notes

- Only transition `transform` and `opacity` for the best performance. They do not trigger layout recalculations.
- Avoid transitioning `width`, `height`, or `top`/`left`. They cause the browser to re-layout the page.
- Keep transition durations under 300ms. Longer animations feel sluggish.
