# HTML Basics: Structure of a Web Page

## Architecture / Rationale

Every HTML page follows the same basic structure. The browser expects certain elements in a certain order to render the page correctly.

Page structure:
- `<!DOCTYPE html>` tells the browser this is an HTML5 document.
- `<html>` is the root element that wraps everything.
- `<head>` holds metadata (title, links to CSS, character set).
- `<body>` holds the visible content of the page.

## Query / Code Blocks

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My First Page</title>
</head>
<body>
    <h1>Hello, world!</h1>
    <p>This is my first web page.</p>
</body>
</html>
```

## Performance / Optimization Notes

- Always include `<!DOCTYPE html>`. Without it, the browser uses quirks mode and your layout may break.
- Set the `lang` attribute on `<html>` for accessibility and SEO.
- Put the `<meta charset="UTF-8">` tag early in the `<head>`. It tells the browser how to decode the text.
