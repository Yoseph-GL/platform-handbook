# CSS Intermediate: Modal Windows

## Architecture / Rationale

A modal is a dialog box that appears on top of the page. It blocks interaction with the rest of the page until the user closes it. Modals combine positioning, z-index, and often a background overlay.

Key techniques:
- The overlay covers the whole screen (`position: fixed` with `inset: 0`).
- The modal box is centered on top of the overlay.
- The `z-index` makes sure the modal stays above everything else.

## Query / Code Blocks

```css
/* Overlay: covers the whole viewport */
.modal-overlay {
    position: fixed;
    inset: 0;
    background: rgba(0, 0, 0, 0.5);
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 1000;
}

/* Modal box */
.modal {
    background: white;
    padding: 32px;
    border-radius: 8px;
    max-width: 500px;
    width: 90%;
    box-shadow: 0 10px 40px rgba(0, 0, 0, 0.2);
}

/* Close button */
.modal__close {
    position: absolute;
    top: 16px;
    right: 16px;
    background: none;
    border: none;
    font-size: 24px;
    cursor: pointer;
}
```

## Performance / Optimization Notes

- Add `overflow: hidden` to the body when the modal is open. It prevents background scrolling.
- Trap keyboard focus inside the modal. Pressing Tab should not reach elements behind the overlay.
- Close the modal when the user presses the Escape key or clicks outside the modal box.
