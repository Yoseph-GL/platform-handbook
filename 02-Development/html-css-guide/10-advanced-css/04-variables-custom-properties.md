# CSS Advanced: Variables (Custom Properties)

## Architecture / Rationale

CSS custom properties (also called CSS variables) store values you can reuse across your stylesheet. They make your CSS more maintainable and dynamic.

- Define with `--name: value;` inside a rule (usually `:root` for global variables).
- Use with `var(--name)` anywhere a value is expected.
- Custom properties cascade. You can override them on a specific element.
- They can be changed at runtime with JavaScript.

## Query / Code Blocks

```css
:root {
    /* Brand colors */
    --color-primary: #3498db;
    --color-primary-dark: #2980b9;
    --color-text: #333;
    --color-bg: #ffffff;

    /* Spacing scale */
    --space-xs: 4px;
    --space-sm: 8px;
    --space-md: 16px;
    --space-lg: 24px;
    --space-xl: 32px;

    /* Typography */
    --font-base: 'Inter', sans-serif;
    --font-size-base: 16px;
}

.button {
    background-color: var(--color-primary);
    padding: var(--space-sm) var(--space-md);
    font-family: var(--font-base);
}

.button:hover {
    background-color: var(--color-primary-dark);
}

/* Override for a dark section */
.dark-section {
    --color-text: #f0f0f0;
    --color-bg: #1a1a1a;
    color: var(--color-text);
    background-color: var(--color-bg);
}
```

## Performance / Optimization Notes

- CSS variables are more powerful than preprocessor variables (Sass/Less). They work at runtime and respond to media queries.
- Use a fallback: `var(--color, red)` uses `red` if `--color` is not defined.
- Do not create too many variables. A design system with 20-30 well-named variables is enough for most projects.
