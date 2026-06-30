# HTML Basics: Lists

## Architecture / Rationale

Lists group related items together. HTML has three types of lists for different kinds of content.

List types:
- `<ul>` (unordered list): items with bullet points. Use when the order does not matter.
- `<ol>` (ordered list): items with numbers. Use when the sequence matters.
- `<dl>` (description list): terms and their definitions.
- `<li>` is used inside `<ul>` and `<ol>` for each list item.

## Query / Code Blocks

```html
<!-- Unordered list: order does not matter -->
<ul>
    <li>HTML</li>
    <li>CSS</li>
    <li>JavaScript</li>
</ul>

<!-- Ordered list: steps in a recipe -->
<ol>
    <li>Preheat the oven to 180°C.</li>
    <li>Mix the flour and sugar.</li>
    <li>Bake for 30 minutes.</li>
</ol>

<!-- Description list: term and definition pairs -->
<dl>
    <dt>HTML</dt>
    <dd>A markup language for web pages.</dd>
    <dt>CSS</dt>
    <dd>A style language for visual design.</dd>
</dl>
```

## Performance / Optimization Notes

- Use `<ol>` when the order of items changes the meaning (recipes, rankings, instructions).
- Lists can be nested. Put a new `<ul>` or `<ol>` inside an `<li>` to create sub-lists.
- Avoid using lists for layout purposes. Use CSS Flexbox or Grid for that.
