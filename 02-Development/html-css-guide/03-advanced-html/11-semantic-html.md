# HTML Advanced: Semantic HTML

## Architecture / Rationale

Semantic HTML uses tags that describe the meaning of the content, not just how it looks. It helps search engines, screen readers, and other developers understand your page.

Semantic tags:
- `<header>`, `<nav>`, `<main>`, `<article>`, `<section>`, `<aside>`, `<footer>`
- These replace generic `<div>` containers. Use `<div>` only when no semantic tag fits.

## Query / Code Blocks

```html
<body>
    <header>
        <nav>
            <a href="/">Home</a>
            <a href="/about">About</a>
        </nav>
    </header>

    <main>
        <article>
            <h1>Article Title</h1>
            <p>Article content goes here.</p>
        </article>

        <aside>
            <h2>Related Articles</h2>
            <ul>
                <li><a href="#">Another post</a></li>
            </ul>
        </aside>
    </main>

    <footer>
        <p>&copy; 2026 My Website</p>
    </footer>
</body>
```

## Performance / Optimization Notes

- Use semantic tags as your first choice. Only fall back to `<div>` when nothing else fits.
- Screen readers can jump between `<nav>`, `<main>`, and `<footer>`. Semantic tags make navigation faster for blind users.
- Search engines give more weight to content inside `<article>` and `<main>`.
