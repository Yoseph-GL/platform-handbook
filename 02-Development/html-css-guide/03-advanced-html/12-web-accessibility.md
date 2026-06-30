# HTML Advanced: Web Accessibility

## Architecture / Rationale

Web accessibility (a11y) means making your site usable by everyone, including people with disabilities. It is not optional — it is a requirement of good web development.

Key practices:
- Use semantic HTML. It gives screen readers a clear page structure.
- Add `alt` text to every image. Describe what the image shows.
- Ensure all interactive elements work with keyboard only (Tab, Enter, Esc).
- Use sufficient color contrast. Text that is too light is hard to read.

## Query / Code Blocks

```html
<!-- Good: semantic structure with alt text and ARIA labels -->
<nav aria-label="Main navigation">
    <ul>
        <li><a href="/">Home</a></li>
        <li><a href="/products">Products</a></li>
    </ul>
</nav>

<main>
    <h1>Our Products</h1>
    <img src="product.jpg" alt="A blue backpack with brown leather straps">

    <button aria-label="Close dialog">
        <span aria-hidden="true">&times;</span>
    </button>
</main>
```

## Performance / Optimization Notes

- Test your page with the Tab key. If you cannot reach every link and button, fix the tab order.
- Use a contrast checker tool. Body text needs at least a 4.5:1 contrast ratio.
- Accessibility improvements benefit everyone, not just users with disabilities. Clear structure and good contrast help all users.
