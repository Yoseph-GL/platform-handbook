# Web Foundations: Understanding HTML and CSS

## Architecture / Rationale

HTML and CSS are the two core languages of the web. They work together but have different jobs.

Key facts:
- **HTML** (HyperText Markup Language) defines the structure and content of a page. It says "this is a heading, this is a paragraph, this is an image."
- **CSS** (Cascading Style Sheets) defines the visual appearance. It says "headings are blue, paragraphs have 16px font, images have rounded corners."
- HTML without CSS is plain but functional. CSS without HTML has nothing to style.

## Query / Code Blocks

```html
<!-- HTML: structure and content -->
<h1>Welcome to my page</h1>
<p>This is a paragraph of text.</p>

<!-- CSS: style and layout -->
<!-- h1 { color: blue; font-size: 24px; } -->
<!-- p  { font-size: 16px; line-height: 1.5; } -->
```

## Performance / Optimization Notes

- Keep HTML and CSS in separate files. Do not mix style inside HTML tags (inline styles).
- HTML handles content and meaning. CSS handles appearance. Respect this separation.
- A well-structured HTML document works even without CSS. A page that only works with styles is fragile.
