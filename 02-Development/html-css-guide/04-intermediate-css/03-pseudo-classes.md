# CSS Intermediate: Pseudo-classes

## Architecture / Rationale

A pseudo-class selects an element that is in a special state. For example, when the mouse hovers over a link, or when an input is focused.

Common pseudo-classes:
- `:hover` — the mouse is over the element.
- `:focus` — the element has keyboard focus.
- `:first-child` / `:last-child` — position among siblings.
- `:nth-child(n)` — pattern-based selection.
- `:not()` — negates a selector.

## Query / Code Blocks

```css
/* Hover effect on links */
a:hover {
    color: #0066cc;
    text-decoration: underline;
}

/* Focus ring on inputs */
input:focus {
    outline: 2px solid #3498db;
    border-color: transparent;
}

/* First and last items in a list */
li:first-child {
    font-weight: bold;
}
li:last-child {
    border-bottom: none;
}

/* Nth child patterns: odd and even rows */
tr:nth-child(odd) {
    background-color: #f5f5f5;
}
tr:nth-child(even) {
    background-color: white;
}

/* Negation: buttons that are NOT primary */
button:not(.primary) {
    background-color: #e0e0e0;
}
```

## Performance / Optimization Notes

- Use `:hover` with a matching `:focus` style. Keyboard users need visual feedback too.
- `:nth-child` counts all siblings, not just siblings of the same type. Use `:nth-of-type` to count only matching elements.
- Complex `:not()` chains can slow selector matching. Keep them simple.
