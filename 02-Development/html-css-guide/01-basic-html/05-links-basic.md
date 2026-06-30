# HTML Basics: Links (Basic)

## Architecture / Rationale

Links connect web pages together. The `<a>` tag (anchor) creates a clickable link. The `href` attribute tells the browser where to go.

Link rules:
- `href` can point to another page on your site (relative path) or to an external site (full URL).
- The link text between the tags is what users see and click.
- Links are blue and underlined by default. Use CSS to change their appearance.

## Query / Code Blocks

```html
<!-- Link to an external website -->
<a href="https://developer.mozilla.org">MDN Web Docs</a>

<!-- Link to another page on your own site -->
<a href="about.html">About Us</a>

<!-- Link that opens in a new tab -->
<a href="https://example.com" target="_blank" rel="noopener">Open in new tab</a>

<!-- Link to a section on the same page -->
<a href="#contact">Jump to Contact</a>
```

## Performance / Optimization Notes

- Use descriptive link text. "Click here" is bad. "Read the HTML specification" is good.
- Add `rel="noopener"` when using `target="_blank"`. It prevents security risks.
- Check your links regularly. Broken links frustrate users and hurt SEO.
