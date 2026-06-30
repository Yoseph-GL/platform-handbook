# CSS Advanced: Calc Function

## Architecture / Rationale

`calc()` lets you mix units in CSS calculations. You can add, subtract, multiply, and divide values of different types.

- `calc(100% - 250px)`: content area next to a fixed sidebar.
- `calc(1rem + 4px)`: precise spacing adjustments.
- `calc(var(--space) * 2)`: math with custom properties.

## Query / Code Blocks

```css
/* Sidebar layout: main fills remaining space */
.main {
    width: calc(100% - 280px);
    margin-left: 280px;
}

/* Half width with gap */
.half {
    width: calc(50% - 16px);
}

/* Fluid spacing */
.hero {
    padding: calc(2rem + 5vw);
}

/* Typography: base size plus viewport scaling */
h2 {
    font-size: calc(1rem + 1vw);
}
```

## Performance / Optimization Notes

- `calc()` is evaluated by the browser at render time. It has negligible performance cost.
- Always put spaces around the operator: `calc(100% - 20px)`. Without spaces, the parser may fail.
- Use `calc()` with custom properties: `calc(var(--space-md) * 2)`. It makes spacing scales easy to implement.
