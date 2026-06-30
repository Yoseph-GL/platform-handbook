# CSS Basics: External Fonts

## Architecture / Rationale

External fonts let you use typefaces that are not installed on the user's computer. Google Fonts is the most popular free font service.

How to use them:
- Link the font in the `<head>` of your HTML, OR import it in your CSS.
- Apply the font with `font-family` in your CSS rules.
- Always include fallback fonts in case the external service is down.

## Query / Code Blocks

```html
<!-- Option 1: Link in HTML <head> -->
<link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap"
      rel="stylesheet">
```

```css
/* Option 2: Import in CSS */
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

body {
    font-family: 'Roboto', sans-serif;
}
```

## Performance / Optimization Notes

- Only load the font weights you actually use. Each weight adds a separate download.
- Use `display=swap` so text appears immediately in a fallback font while the custom font loads.
- Self-host fonts when possible. It gives you more control and can be faster than external services.
