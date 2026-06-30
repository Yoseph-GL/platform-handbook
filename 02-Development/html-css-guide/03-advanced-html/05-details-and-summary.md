# HTML Advanced: Details and Summary

## Architecture / Rationale

The `<details>` and `<summary>` elements create a collapsible section. The user clicks the summary to show or hide the content. No JavaScript needed.

- `<details>` wraps the entire collapsible section.
- `<summary>` is the clickable heading. It is always visible.
- The content after `<summary>` is hidden until the user clicks.

## Query / Code Blocks

```html
<details>
    <summary>How do I reset my password?</summary>
    <p>Go to the login page and click "Forgot password". You will receive an email with a reset link.</p>
</details>

<details open>
    <summary>This section is open by default</summary>
    <p>Use the <code>open</code> attribute to show the content on page load.</p>
</details>

<details>
    <summary>Shipping information</summary>
    <p>We ship to over 50 countries. Delivery takes 5-10 business days.</p>
</details>
```

## Performance / Optimization Notes

- Use `<details>` for FAQs, spoilers, or progressive disclosure of complex information.
- The `open` attribute makes the section start expanded. Use it when the information is important for most users.
- Multiple `<details>` elements work independently. Opening one does not close the others.
