# HTML Advanced: Links (Advanced)

## Architecture / Rationale

Links can do more than navigate between pages. They can open email programs, trigger phone calls, link to specific parts of a page, and indicate download files.

- `mailto:` opens the user's email application.
- `tel:` starts a phone call on mobile devices.
- `#section-id` jumps to an element on the same page.
- The `download` attribute suggests the browser save the linked file.

## Query / Code Blocks

```html
<!-- Email link -->
<a href="mailto:hello@example.com?subject=Question">Send us an email</a>

<!-- Phone link (works on mobile) -->
<a href="tel:+521234567890">Call us</a>

<!-- Jump to a section on the same page -->
<a href="#faq">Go to FAQ</a>
<h2 id="faq">Frequently Asked Questions</h2>

<!-- Download link -->
<a href="files/brochure.pdf" download>Download brochure (PDF)</a>

<!-- Link that opens in a new tab (safe way) -->
<a href="https://example.com" target="_blank" rel="noopener noreferrer">External site</a>
```

## Performance / Optimization Notes

- Always add `rel="noopener noreferrer"` when using `target="_blank"`. It prevents security and performance issues.
- Use `download` only for files you control. It does not work for cross-origin links.
- Check that anchor links (`#section`) match the correct `id` values on the page.
