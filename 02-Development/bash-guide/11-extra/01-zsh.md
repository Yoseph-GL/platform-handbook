# Bash Extra: Zsh

## Architecture / Rationale

Zsh (Z Shell) is an alternative shell that extends Bash with better autocompletion, theming, and plugin support. It is the default shell on macOS since Catalina.

Key Zsh features:
- Better tab completion with menus.
- Built-in spelling correction.
- Right-side prompt (`RPROMPT`).
- Plugin frameworks like Oh My Zsh.
- Backwards-compatible with Bash scripts.

## Query / Code Blocks

```bash
# Check if Zsh is installed
which zsh

# Switch to Zsh (temporary)
zsh

# Make Zsh your default shell (permanent)
chsh -s $(which zsh)

# Install Oh My Zsh (popular plugin framework)
# sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

# Zsh specific features:
# - Type part of a folder name and press Tab twice for a menu
# - Type "cd /u/l/b" and press Tab → becomes "cd /usr/local/bin"
# - Spelling correction: "sl" → "ls"
```

## Performance / Optimization Notes

- Zsh runs Bash scripts without changes. Your `.sh` files work the same.
- Oh My Zsh adds many features but can slow down shell startup. Start with plain Zsh first.
- Learn Bash first, then explore Zsh. The fundamentals are the same across both shells.
