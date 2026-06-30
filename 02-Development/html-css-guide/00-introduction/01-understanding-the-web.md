# Web Foundations: Understanding the Web

## Architecture / Rationale

The web is a network of documents connected by links. A browser requests a page from a server, the server sends back HTML, and the browser renders it.

Key facts:
- The web uses HTTP (HyperText Transfer Protocol) to send data between browsers and servers.
- Every web page has a URL (Uniform Resource Locator) that tells the browser where to find it.
- The browser parses HTML, loads CSS and JavaScript, and draws the page on your screen.

## Query / Code Blocks

```html
<!-- A web page is just a text file with HTML tags.
     The browser reads it and builds the page you see. -->
<!-- Placeholder: basic HTTP request/response diagram -->
```

## Performance / Optimization Notes

- Understand the request-response cycle before writing HTML. It helps you design faster pages.
- Every file your page loads (CSS, images, fonts) needs a separate HTTP request. Fewer files means faster loading.
- The browser caches files it has already downloaded. Use this to your advantage when designing a site.
