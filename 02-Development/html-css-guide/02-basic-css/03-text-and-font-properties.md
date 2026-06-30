# CSS Basics: Text and Font Properties

## Architecture / Rationale

CSS gives you fine control over how text looks. Font properties define the typeface, size, weight, and style of text.

Key font properties:
- `font-family`: the typeface (Arial, Georgia, sans-serif).
- `font-size`: how big the text is.
- `font-weight`: boldness (normal, bold, or a number like 700).
- `font-style`: normal or italic.
- `text-align`: left, center, right, or justify.
- `line-height`: space between lines of text.

## Query / Code Blocks

```css
body {
    font-family: 'Segoe UI', Tahoma, sans-serif;
    font-size: 16px;
    line-height: 1.6;
    color: #333;
}

h1 {
    font-size: 32px;
    font-weight: 700;
    text-align: center;
}

p {
    margin-bottom: 1em;
}
```

## Performance / Optimization Notes

- Always provide a fallback font stack. If the first font is not available, the browser tries the next one.
- Use relative units (`em`, `rem`) for font sizes. They respect user zoom preferences.
- Do not use too many different fonts on one page. Each font file adds download time.
