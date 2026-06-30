# CSS Basics: Padding and Margin

## Architecture / Rationale

Padding and margin create space around elements. They look similar but serve different purposes.

- **Padding** is inside the border. It pushes the content away from the border. It shares the element's background color.
- **Margin** is outside the border. It pushes other elements away. It is always transparent.

## Query / Code Blocks

```css
.card {
    /* Space inside the card, around the text */
    padding: 24px;

    /* Space outside the card, between cards */
    margin: 16px;

    /* Individual sides: top right bottom left */
    padding: 10px 20px 10px 20px;

    /* Individual properties */
    margin-top: 20px;
    margin-bottom: 10px;
}
```

## Performance / Optimization Notes

- Use padding for space inside components and margin for space between components. Keep the purpose clear.
- Vertical margins collapse: when two margins meet, the larger one wins. Padding does not collapse.
- Use a consistent spacing scale (4px, 8px, 16px, 24px, 32px) across your whole project.
