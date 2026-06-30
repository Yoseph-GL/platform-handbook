# Bash Basic Editors: Vim

## Architecture / Rationale

Vim is a modal editor. It has different modes for inserting text, running commands, and selecting content. This design lets you edit without moving your hands from the keyboard.

Vim modes:
- **Normal mode**: for navigation and commands. Press `Esc` to return here.
- **Insert mode**: for typing text. Press `i` to enter.
- **Visual mode**: for selecting text. Press `v` to enter.
- **Command mode**: for saving and quitting. Press `:` from normal mode.

## Query / Code Blocks

```bash
# Open a file in Vim
vim file.txt

# Essential Vim commands (in Normal mode, press Esc first):
# i        - enter Insert mode (start typing)
# Esc      - return to Normal mode
# :w       - save (write)
# :q       - quit
# :wq      - save and quit
# :q!      - quit without saving
# dd       - delete a line
# yy       - copy a line
# p        - paste
# /search  - search for text
# u        - undo
# Ctrl+R   - redo
```

## Performance / Optimization Notes

- The first Vim lesson: how to exit. Press `Esc`, then type `:q!` and press Enter.
- Run `vimtutor` in your terminal. It is a 30-minute interactive tutorial that teaches the basics.
- Vim's power comes from composing commands. `d3w` means "delete 3 words". This composability is what makes it fast.
