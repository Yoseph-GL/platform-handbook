# CSS Basics: Selectors (Basic)

## Architecture / Rationale

A selector tells CSS which elements to style. Basic selectors target elements by name, class, or ID.

Selector types:
- **Element selector**: targets all elements of that type (`p`, `h1`, `div`).
- **Class selector**: targets elements with a specific class (`.highlight`). Classes can be reused.
- **ID selector**: targets one unique element (`#header`). An ID must be unique on the page.

## Query / Code Blocks

```css
/* Element selector: all paragraphs */
p {
    font-size: 16px;
}

/* Class selector: any element with class "highlight" */
.highlight {
    background-color: yellow;
}

/* ID selector: the element with id "main-title" */
#main-title {
    text-align: center;
}

/* Combine selector: paragraphs with class "intro" */
p.intro {
    font-weight: bold;
}
```

## Performance / Optimization Notes

- Prefer class selectors over ID selectors for styling. Classes are reusable and have lower specificity.
- Avoid chaining too many selectors (`div.container ul.list li.item`). It makes your CSS fragile.
- Browsers read selectors from right to left. Short, specific selectors are faster to match.
