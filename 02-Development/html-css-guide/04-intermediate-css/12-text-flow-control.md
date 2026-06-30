# CSS Intermediate: Text Flow Control

## Architecture / Rationale

CSS gives you fine control over how text flows inside its container. These properties handle wrapping, spacing, and alignment.

Key properties:
- `white-space`: how whitespace and line breaks are handled.
- `word-break`: whether words can break mid-word.
- `word-wrap` / `overflow-wrap`: whether long words can break to the next line.
- `hyphens`: enables automatic hyphenation.

## Query / Code Blocks

```css
/* Prevent text from wrapping */
.no-wrap {
    white-space: nowrap;
}

/* Allow breaking inside long words */
.long-content {
    overflow-wrap: break-word;
    word-break: break-word;
}

/* Preserve line breaks from user input (like in a textarea) */
.preserve-breaks {
    white-space: pre-wrap;
}

/* Automatic hyphenation */
.hyphenate {
    hyphens: auto;
    /* Requires lang attribute on <html> */
}
```

## Performance / Optimization Notes

- Use `overflow-wrap: break-word` on containers that might receive long user-generated text like emails or URLs.
- `white-space: nowrap` is useful for navigation links or code snippets that should stay on one line.
- Avoid using `word-break: break-all` unless you really need to break at any character. It can make text harder to read.
