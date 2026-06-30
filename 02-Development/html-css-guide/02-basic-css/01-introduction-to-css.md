# CSS Basics: Introduction to CSS

## Architecture / Rationale

CSS (Cascading Style Sheets) controls how HTML elements look. You write rules that select elements and set their visual properties.

Ways to add CSS:
- Inline: inside a `style` attribute on one element. Avoid this for anything more than quick tests.
- Internal: inside a `<style>` tag in the `<head>`. Good for single-page demos.
- External: in a separate `.css` file linked with `<link>`. This is the standard way.

## Query / Code Blocks

```html
<!-- External CSS: link a stylesheet in the <head> -->
<link rel="stylesheet" href="styles.css">
```

```css
/* styles.css — your first CSS rule */
h1 {
    color: darkblue;
    font-size: 28px;
}

p {
    color: #333;
    line-height: 1.6;
}
```

## Performance / Optimization Notes

- Always use external CSS files. The browser downloads them once and caches them for all pages.
- Put CSS in the `<head>`. If it loads late, the page flashes unstyled content.
- One CSS file for a small site is fine. For large projects, split styles into multiple files by component.
