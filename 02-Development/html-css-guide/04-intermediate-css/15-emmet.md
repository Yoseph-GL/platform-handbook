# CSS Intermediate: Emmet

## Architecture / Rationale

Emmet is a shorthand syntax built into most code editors. It expands short abbreviations into full HTML and CSS code. It saves hours of typing.

Common Emmet patterns:
- `ul>li*5` → a `<ul>` with five `<li>` children.
- `div.container>div.card*3` → three cards inside a container.
- CSS: `m20` → `margin: 20px;`, `bgc` → `background-color: #fff;`.

## Query / Code Blocks

```html
<!-- Emmet input: .card>img[src="photo.jpg"][alt="Photo"]+h2{Title}+p{Description}
     Expands to: -->

<div class="card">
    <img src="photo.jpg" alt="Photo">
    <h2>Title</h2>
    <p>Description</p>
</div>
```

```css
/* Emmet input: w100p+h200+m0-a+bdrs8
   Expands to: */

width: 100%;
height: 200px;
margin: 0 auto;
border-radius: 8px;
```

## Performance / Optimization Notes

- Emmet is built into VS Code by default. Start typing an abbreviation and press Tab to expand it.
- Learn the CSS abbreviations first. They save the most time because CSS has so many repetitive properties.
- Emmet does not affect your output. It is purely a typing shortcut. The browser never sees it.
