# CSS Intermediate: Outline

## Architecture / Rationale

`outline` is similar to `border` but does not take up space. It draws a line around the element without affecting the layout.

Key facts:
- Outline does not add to the element's size (unlike border).
- Outline is commonly used for focus indicators on interactive elements.
- `outline-offset` adds space between the element and its outline.

## Query / Code Blocks

```css
/* Focus indicator for keyboard users */
button:focus-visible {
    outline: 2px solid #3498db;
    outline-offset: 2px;
}

/* Remove default outline but add a custom one */
input:focus {
    outline: none;
    border-color: #3498db;
    box-shadow: 0 0 0 3px rgba(52, 152, 219, 0.3);
}

/* Debug: show all element outlines */
* {
    outline: 1px solid red !important;
}
```

## Performance / Optimization Notes

- Never remove `:focus` outlines without providing a visible alternative. Keyboard users need to see which element is focused.
- Use `:focus-visible` instead of `:focus` to show outlines only to keyboard users, not mouse clickers.
- Outline does not affect layout — use it for accessibility without worrying about breaking your design.
