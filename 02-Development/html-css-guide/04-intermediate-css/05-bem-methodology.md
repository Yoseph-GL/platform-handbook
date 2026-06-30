# CSS Intermediate: BEM Methodology

## Architecture / Rationale

BEM (Block, Element, Modifier) is a naming convention for CSS classes. It makes your styles predictable and easy to understand in large projects.

BEM structure:
- **Block**: a standalone component (`.card`, `.button`).
- **Element**: a part of the block (`.card__title`, `.button__icon`).
- **Modifier**: a variant of the block (`.card--featured`, `.button--large`).

## Query / Code Blocks

```css
/* Block */
.card {
    padding: 20px;
    border-radius: 8px;
    background: white;
}

/* Elements */
.card__title {
    font-size: 18px;
    font-weight: bold;
}
.card__body {
    font-size: 14px;
    color: #666;
}
.card__button {
    padding: 10px 16px;
}

/* Modifier */
.card--featured {
    border: 2px solid #f39c12;
}
.card--dark {
    background: #333;
    color: white;
}
```

## Performance / Optimization Notes

- BEM class names are long but predictable. You always know what an element belongs to.
- Never nest BEM selectors in CSS (like `.card .card__title`). It increases specificity for no reason. Use `.card__title` directly.
- BEM works at any project size. Even small projects benefit from clear class names.
