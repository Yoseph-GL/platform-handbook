# CSS Animations: Transitions Recap

## Architecture / Rationale

Transitions are the simplest form of animation in CSS. They smoothly change a property value when the element changes state (hover, focus, class change).

- Transitions animate from one value to another over time.
- They need a trigger: a pseudo-class (`:hover`, `:focus`) or a class added by JavaScript.
- Key properties: `transition-property`, `transition-duration`, `transition-timing-function`.

## Query / Code Blocks

```css
.button {
    background-color: #3498db;
    transition: background-color 0.3s ease,
                transform 0.2s ease,
                box-shadow 0.3s ease;
}

.button:hover {
    background-color: #2980b9;
    transform: translateY(-2px);
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2);
}
```

## Performance / Optimization Notes

- Stick to `opacity` and `transform` for the smoothest transitions. Avoid animating `width`, `height`, or `top`/`left`.
- Use `ease` or `ease-out` for most transitions. Linear motion looks robotic.
- Keep transitions under 300ms. Shorter durations feel more responsive.
