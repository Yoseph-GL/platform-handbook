# HTML Basics: Paragraphs and Headings

## Architecture / Rationale

Headings and paragraphs are the most common text elements in HTML. They give structure and hierarchy to your content.

Usage rules:
- `<h1>` is the main heading of the page. Use it once per page.
- `<h2>` through `<h6>` are subheadings. Use them in order.
- `<p>` defines a paragraph of text.
- The browser adds spacing above and below headings and paragraphs by default.

## Query / Code Blocks

```html
<h1>Main Title of the Page</h1>
<p>This is the first paragraph. It introduces the topic.</p>

<h2>Section Title</h2>
<p>This paragraph belongs to the section above. Each paragraph is a block of related sentences.</p>

<h3>Sub-section Title</h3>
<p>Another paragraph with more details about the sub-section.</p>
```

## Performance / Optimization Notes

- Do not skip heading levels (`h1` → `h3` without `h2`). Screen readers rely on the hierarchy.
- Use headings for structure, not for font size. Use CSS to change the visual size.
- Keep paragraphs short. Large blocks of text are hard to read on screens.
