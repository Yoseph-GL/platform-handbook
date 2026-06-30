# CSS Intermediate: Inheritance, Cascade and Specificity

## Architecture / Rationale

These three concepts decide which styles apply when multiple rules target the same element. Understanding them prevents the most common CSS frustrations.

- **Inheritance**: some properties (like `color` and `font-family`) pass from parent to child automatically.
- **Cascade**: when multiple rules have the same specificity, the last one wins.
- **Specificity**: a score calculated from the selector. Higher specificity wins over lower specificity.

Specificity hierarchy (lowest to highest):
1. Element selectors (`p`, `h1`).
2. Class, attribute, and pseudo-class selectors (`.card`, `[type]`, `:hover`).
3. ID selectors (`#header`).
4. Inline styles and `!important`.

## Query / Code Blocks

```css
/* Low specificity: (0, 0, 1) */
p {
    color: black;
}

/* Medium specificity: (0, 1, 0) */
.intro {
    color: blue;
}

/* High specificity: (1, 0, 0) */
#main-paragraph {
    color: red;
}

/* Higher: (0, 1, 1) */
p.intro {
    color: green;
}

/* ⚠️ Avoid !important. It breaks the cascade and is hard to override. */
p {
    color: orange !important;
}
```

## Performance / Optimization Notes

- Use class selectors for styling. They have consistent specificity and are easy to override.
- Avoid ID selectors in CSS. Their high specificity makes them hard to override later.
- Never use `!important` unless you are in a debugging emergency. Even then, fix the root cause afterward.
