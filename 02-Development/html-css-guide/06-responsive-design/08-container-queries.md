# CSS Responsive: Container Queries

## Architecture / Rationale

Container queries let an element adapt to the size of its parent container, not the viewport. This is a game-changer for reusable components.

- A media query asks "how wide is the screen?"
- A container query asks "how wide is my container?"
- Components become truly independent. The same component works in a sidebar and a full-width main area.

## Query / Code Blocks

```css
/* Define a containment context */
.card-wrapper {
    container-type: inline-size;
    container-name: card;
}

/* Style the card based on the container width */
@container card (min-width: 400px) {
    .card {
        display: flex;
        flex-direction: row;
        gap: 16px;
    }
    .card__image {
        width: 40%;
    }
}
```

## Performance / Optimization Notes

- Container queries are supported in all modern browsers (Chrome 105+, Safari 16+, Firefox 110+).
- Use container queries for design system components. They make components truly reusable.
- `container-type: inline-size` is the most common. Only use `size` if you need height-based queries (rare).
