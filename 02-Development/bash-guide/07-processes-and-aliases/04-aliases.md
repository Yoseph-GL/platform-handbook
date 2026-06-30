# Bash Processes: Aliases

## Architecture / Rationale

An alias is a shortcut for a command. Instead of typing a long command every time, you give it a short name.

- `alias name='command'` — creates a temporary alias.
- Add aliases to `~/.bashrc` to make them permanent.
- `unalias name` — removes an alias.
- `alias` without arguments lists all current aliases.

## Query / Code Blocks

```bash
# Create a temporary alias
alias ll='ls -la'

# Create an alias with options
alias grep='grep --color=auto'

# Common useful aliases
alias ..='cd ..'
alias ...='cd ../..'
alias c='clear'
alias ports='netstat -tulanp'

# List all aliases
alias

# Remove an alias
unalias ll

# Permanent aliases go in ~/.bashrc (open and add them)
# Example ~/.bashrc lines:
# alias ll='ls -la'
# alias update='sudo apt update && sudo apt upgrade'
```

## Performance / Optimization Notes

- Aliases are for interactive use, not for scripts. Scripts should use the full command names.
- Put all your aliases in one place: `~/.bashrc` or a separate `~/.bash_aliases` file.
- Check for conflicts: `type <name>` tells you if an alias already exists with that name.
