# CSS Advanced: Transform

## Architecture / Rationale

`transform` moves, rotates, scales, and skews elements without affecting the document flow. Transforms happen on the GPU and are the most performant way to animate movement.

Transform functions:
- `translate(x, y)` — move horizontally and vertically.
- `rotate(deg)` — rotate around the center.
- `scale(x, y)` — resize.
- `skew(x, y)` — slant.
- `translateZ(z)` — move in 3D space (requires `perspective` on the parent).

## Query / Code Blocks

```css
/* Center an element perfectly */
.centered {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}

/* Scale on hover */
.card:hover {
    transform: scale(1.05);
    transition: transform 0.3s ease;
}

/* Rotate an icon */
.icon-rotated {
    transform: rotate(45deg);
}

/* Multiple transforms */
.badge {
    transform: translateY(-10px) rotate(-5deg) scale(1.1);
}
```

## Performance / Optimization Notes

- `transform` does not trigger layout recalculations. It is the best property to animate.
- `translate(-50%, -50%)` with `top: 50%; left: 50%` is the classic CSS centering trick.
- Use `will-change: transform` on elements that will animate frequently to hint the browser to pre-optimize.
