# HTML Advanced: Textarea and Labels

## Architecture / Rationale

`<textarea>` lets users type multiple lines of text. It is different from `<input type="text">` which only allows one line. Labels improve accessibility by connecting text descriptions to form fields.

- `<textarea>` has `rows` and `cols` attributes to set its size.
- The `<label>` tag uses the `for` attribute to link to an input's `id`. Clicking the label focuses the field.
- Always connect labels to their inputs.

## Query / Code Blocks

```html
<form>
    <label for="name">Your name:</label>
    <input type="text" id="name" name="name">

    <label for="bio">Tell us about yourself:</label>
    <textarea id="bio" name="bio" rows="5" cols="30" placeholder="Write here..."></textarea>

    <button type="submit">Send</button>
</form>
```

## Performance / Optimization Notes

- Use `placeholder` to give users a hint, but never use it instead of a `<label>`.
- The `rows` and `cols` set the initial size. Use CSS `width` and `height` for precise control.
- Textarea content can include line breaks. They are preserved when the form is submitted.
