# HTML Advanced: Deprecated HTML

## Architecture / Rationale

Some HTML tags and attributes are deprecated. They still work in browsers but should not be used in new projects. CSS and modern HTML replace their functionality.

Examples of deprecated elements:
- `<font>` — use CSS `font-family` instead.
- `<center>` — use CSS `text-align: center` or Flexbox instead.
- `<marquee>` — use CSS animations if you really need scrolling text.
- `<b>` and `<i>` without semantic meaning — use `<strong>` and `<em>`, or CSS for visual styling.

## Query / Code Blocks

```html
<!-- ❌ Deprecated: do not use these -->
<font color="red">This text is red.</font>
<center>Centered content</center>
<marquee>Scrolling text (avoid this)</marquee>

<!-- ✅ Modern alternatives -->
<p style="color: red;">This text is red via CSS.</p>
<p style="text-align: center;">This is centered via CSS.</p>
```

## Performance / Optimization Notes

- Deprecated tags can be removed from browsers in the future. Your page will break if that happens.
- Always use the modern equivalent from HTML5 and CSS3.
- If you see deprecated tags in old tutorials, find a newer resource.
