# HTML Advanced: Fieldset and Legend

## Architecture / Rationale

`<fieldset>` groups related form controls together visually and semantically. The `<legend>` gives the group a title. Both improve form readability and accessibility.

- `<fieldset>` draws a border around its children by default.
- `<legend>` is the caption for the fieldset. It appears inside the border.
- Use fieldsets to break long forms into sections.

## Query / Code Blocks

```html
<form>
    <fieldset>
        <legend>Personal Information</legend>

        <label for="firstname">First name:</label>
        <input type="text" id="firstname" name="firstname">

        <label for="lastname">Last name:</label>
        <input type="text" id="lastname" name="lastname">
    </fieldset>

    <fieldset>
        <legend>Contact Details</legend>

        <label for="email">Email:</label>
        <input type="email" id="email" name="email">
    </fieldset>

    <button type="submit">Submit</button>
</form>
```

## Performance / Optimization Notes

- Screen readers announce the `<legend>` text before each input in the fieldset. It helps users understand the context.
- You can style fieldsets and legends with CSS. The default border can be removed with `border: none`.
- Split forms with more than 6 fields into multiple fieldsets. It reduces visual overwhelm.
