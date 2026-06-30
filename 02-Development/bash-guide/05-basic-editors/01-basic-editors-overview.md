# Bash Basic Editors: Overview

## Architecture / Rationale

A terminal text editor runs inside the terminal. It has no mouse, no menus, and no graphics. You control everything with the keyboard.

Common terminal editors:
- **Nano**: simple, shows shortcuts at the bottom. Best for beginners.
- **Vim**: powerful, modal editing. Steep learning curve, very fast once learned.
- **Neovim**: a modern rewrite of Vim with better plugin support.
- **Emacs**: an extensible editor that can do almost anything, including email and games.

## Query / Code Blocks

```bash
# Open a file in Nano
nano file.txt

# Open a file in Vim
vim file.txt

# Open a file in Neovim
nvim file.txt

# Open a file in Emacs (terminal mode)
emacs -nw file.txt
```

## Performance / Optimization Notes

- Start with Nano. It is the easiest to learn and is installed everywhere.
- If you plan to do a lot of remote server work, learn Vim. It is the default on most servers.
- Editors are personal tools. Try a few and pick the one that feels best to you.
