# Bash Basic Editors: Other Editors

## Architecture / Rationale

Beyond Nano and Vim, there are other terminal editors worth knowing about. They offer modern features and different editing philosophies.

- **Neovim**: a fork of Vim with better plugin architecture, built-in LSP support, and Lua scripting. Most Vim plugins work in Neovim.
- **Emacs**: a full environment, not just an editor. It has a file manager, terminal, email client, and games. Uses Lisp for configuration.
- **Helix**: a newer modal editor with built-in LSP and tree-sitter. No configuration needed for basic use.

## Query / Code Blocks

```bash
# Neovim
nvim file.txt

# Emacs (terminal mode, no window)
emacs -nw file.txt

# Emacs basics:
# Ctrl+X Ctrl+S - save
# Ctrl+X Ctrl+C - exit
# Ctrl+G - cancel current command
```

## Performance / Optimization Notes

- Neovim is a drop-in replacement for Vim. Your Vim knowledge transfers 100%.
- Emacs is worth trying after you are comfortable with Bash. Its integrated approach can replace many separate terminal tools.
- Choose one editor for daily work. Switching editors every week prevents you from building speed.
