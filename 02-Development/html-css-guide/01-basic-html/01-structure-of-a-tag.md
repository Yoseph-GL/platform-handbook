# HTML Basics: Structure of a Tag

## Architecture / Rationale

An HTML tag marks a piece of content with a meaning. Most tags come in pairs: an opening tag and a closing tag. The content goes between them.

Tag rules:
- An opening tag has angle brackets: `<tagname>`.
- A closing tag has a slash: `</tagname>`.
- Some tags are self-closing (they have no content inside): `<img>`, `<br>`, `<input>`.
- Tags can have attributes that give extra information: `<a href="url">`.

## Query / Code Blocks

```html
<!-- Basic tag structure: opening tag, content, closing tag -->
<p>This is a paragraph.</p>

<!-- Tag with an attribute -->
<a href="https://example.com">Click here</a>

<!-- Self-closing tag (no content, no closing tag needed) -->
<img src="photo.jpg" alt="A photo">
<br>
```

## Performance / Optimization Notes

- Always close your tags. Even when the browser guesses correctly, unclosed tags cause layout bugs.
- Write attribute values in double quotes: `href="page.html"`. It prevents errors with special characters.
- Use lowercase for tag names and attribute names. It is the modern standard.
