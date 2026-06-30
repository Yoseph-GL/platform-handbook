# HTML Advanced: Tables

## Architecture / Rationale

Tables display data in rows and columns. They should only be used for tabular data, not for page layout.

Table structure:
- `<table>` wraps the entire table.
- `<thead>` holds the header row(s).
- `<tbody>` holds the data rows.
- `<tr>` is a table row. `<th>` is a header cell. `<td>` is a data cell.

## Query / Code Blocks

```html
<table>
    <thead>
        <tr>
            <th>Product</th>
            <th>Price</th>
            <th>In Stock</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Laptop</td>
            <td>$999</td>
            <td>Yes</td>
        </tr>
        <tr>
            <td>Monitor</td>
            <td>$299</td>
            <td>No</td>
        </tr>
    </tbody>
</table>
```

## Performance / Optimization Notes

- Use tables for data, not for page layout. Layout is for CSS Grid and Flexbox.
- Add `<th scope="col">` or `<th scope="row">` to help screen readers navigate tables.
- For large tables, consider adding a horizontal scroll container on mobile screens.
