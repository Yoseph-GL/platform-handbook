# HTML Advanced: Metatags, Comments and Icons

## Architecture / Rationale

Metatags give information about your page to browsers and search engines. Comments help you document your code. Icons make your page recognizable in tabs and bookmarks.

- `<meta>` tags live in the `<head>`. They set the character set, viewport, description, and keywords.
- HTML comments use `<!-- -->` syntax. The browser ignores them.
- A favicon is the small icon shown in the browser tab. Use `<link rel="icon">` to add one.

## Query / Code Blocks

```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="A personal learning site about web development.">
    <meta name="keywords" content="HTML, CSS, tutorial">

    <!-- Favicon -->
    <link rel="icon" href="favicon.ico" type="image/x-icon">
</head>
<body>
    <!-- This is a comment. It is not visible on the page. -->

    <!-- TODO: add a navigation bar here -->
</body>
```

## Performance / Optimization Notes

- A good `<meta name="description">` improves how your page looks in search results.
- The viewport meta tag is required for responsive design. Without it, mobile browsers zoom out.
- Keep comments short and useful. Remove old TODO comments before publishing.
