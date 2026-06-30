# CSS Animations: Animated Buttons and Typewriter Effect

## Architecture / Rationale

These are two classic CSS animation examples. Animated buttons provide satisfying feedback on interaction. The typewriter effect mimics typing text.

- Buttons use `:hover` and `:active` with transitions and transforms.
- The typewriter effect uses `@keyframes` to change the width of text and a blinking cursor with `border-right`.

## Query / Code Blocks

```css
/* Animated button */
.button {
    padding: 14px 28px;
    background: linear-gradient(135deg, #667eea, #764ba2);
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
    transition: transform 0.2s, box-shadow 0.2s;
}
.button:hover {
    transform: translateY(-3px);
    box-shadow: 0 6px 20px rgba(102, 126, 234, 0.4);
}
.button:active {
    transform: translateY(-1px);
}

/* Typewriter effect */
@keyframes typing {
    from { width: 0; }
    to   { width: 100%; }
}

@keyframes blink-caret {
    from, to { border-color: transparent; }
    50%      { border-color: black; }
}

.typewriter {
    overflow: hidden;
    white-space: nowrap;
    border-right: 3px solid black;
    width: 0;
    animation: typing 3s steps(40) 1s forwards,
               blink-caret 0.75s step-end infinite;
}
```

## Performance / Optimization Notes

- Use `:active` to give immediate feedback on click. It makes buttons feel faster.
- The typewriter effect uses `steps()`, not `ease`. Steps create the character-by-character look.
- Keep decorative animations subtle. They should not compete with content for attention.
