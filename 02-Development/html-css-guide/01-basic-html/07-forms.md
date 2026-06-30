# HTML Basics: Forms

## Architecture / Rationale

Forms let users send data to a server. Every login box, search bar, and contact page uses a form.

Form rules:
- `<form>` wraps all the input elements.
- `<input>` is the most common form element. Its `type` attribute defines what kind of input it is.
- `<label>` describes each input. Clicking the label focuses the input.
- A submit button sends the data to the server.

## Query / Code Blocks

```html
<form action="/submit" method="post">
    <label for="name">Name:</label>
    <input type="text" id="name" name="name" required>

    <label for="email">Email:</label>
    <input type="email" id="email" name="email" required>

    <label for="message">Message:</label>
    <textarea id="message" name="message" rows="4"></textarea>

    <button type="submit">Send</button>
</form>
```

## Performance / Optimization Notes

- Always pair `<label>` with its input using the `for` and `id` attributes. It helps screen readers and touch targets.
- Use the right input type (`email`, `number`, `tel`). The browser validates it and shows the right keyboard on mobile.
- Add the `required` attribute to fields that must be filled in. The browser blocks submission if they are empty.
