# HTML Advanced: Select, Datalist and Option

## Architecture / Rationale

These elements let users choose from a list of options instead of typing freely.

- `<select>` creates a dropdown menu. Each `<option>` inside is one choice.
- `<datalist>` provides suggestions for an `<input>`. The user can still type their own value.
- Use `<optgroup>` to group related options in a long select.

## Query / Code Blocks

```html
<!-- Select dropdown -->
<label for="country">Country:</label>
<select id="country" name="country">
    <option value="">-- Choose a country --</option>
    <option value="mx">Mexico</option>
    <option value="ar">Argentina</option>
    <option value="es">Spain</option>
</select>

<!-- Datalist: suggestions for an input -->
<label for="browser">Browser:</label>
<input list="browsers" id="browser" name="browser">
<datalist id="browsers">
    <option value="Chrome">
    <option value="Firefox">
    <option value="Safari">
</datalist>
```

## Performance / Optimization Notes

- Use `<select>` when the user must pick from a fixed set of options.
- Use `<datalist>` when you want to suggest values but still allow free input.
- Long `<select>` dropdowns are hard to use on mobile. If there are more than 15 options, consider a search input instead.
