# CSS Intermediate: Pseudo-elements

## Architecture / Rationale

A pseudo-element creates a virtual element that you can style without adding extra HTML. They are written with double colons (`::`).

Common pseudo-elements:
- `::before` — inserts content before the element.
- `::after` — inserts content after the element.
- `::first-letter` — styles the first character.
- `::first-line` — styles the first line of text.
- `::selection` — styles text selected by the user.

## Query / Code Blocks

```css
/* Add an icon before a link */
a[href^="https"]::before {
    content: "↗ ";
    font-size: 0.8em;
}

/* Style the first letter of a paragraph */
p.intro::first-letter {
    font-size: 3em;
    font-weight: bold;
    color: #3498db;
    float: left;
    margin-right: 8px;
}

/* Style selected text */
::selection {
    background-color: #3498db;
    color: white;
}

/* Clearfix pattern with ::after */
.clearfix::after {
    content: "";
    display: table;
    clear: both;
}
```

## Performance / Optimization Notes

- `::before` and `::after` always need the `content` property, even if it is empty.
- Pseudo-elements are not in the DOM. Screen readers may ignore their content. Do not put critical information in `content`.
- Avoid animating pseudo-elements heavily. They trigger repaints just like real elements.
