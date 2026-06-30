# Bash Basic Editors: Nano

## Architecture / Rationale

Nano is the simplest terminal text editor. It shows keyboard shortcuts at the bottom of the screen. You can start typing immediately — no modes, no commands to learn first.

Key shortcuts (shown at the bottom as `^X` meaning Ctrl+X):
- `Ctrl+O` — save (Write Out).
- `Ctrl+X` — exit.
- `Ctrl+K` — cut a line.
- `Ctrl+U` — paste (uncut).
- `Ctrl+W` — search (Where is).
- `Ctrl+\` — search and replace.

## Query / Code Blocks

```bash
# Open or create a file
nano notes.txt

# Open a file at a specific line number
nano +25 script.sh

# Open in read-only mode (prevent saving)
nano -v config.conf
```

## Performance / Optimization Notes

- Nano is the best choice for quick edits. Open, type, Ctrl+O, Ctrl+X — done in seconds.
- The `^` symbol means the Ctrl key. `^O` is Ctrl+O, not Shift+6+O.
- Nano is almost always installed on Linux servers. If Vim is not available, Nano will be.
