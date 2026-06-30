# Bash Processes: History

## Architecture / Rationale

Bash keeps a history of every command you type. You can search it, reuse commands, and save time typing.

- `history` — shows your recent commands.
- `!!` — repeat the last command.
- `!$` — use the last argument of the previous command.
- `Ctrl+R` — search your history interactively.
- `↑` and `↓` — navigate through history line by line.

## Query / Code Blocks

```bash
# Show recent commands
history

# Show the last 20 commands
history 20

# Repeat the last command
!!

# Repeat a command by its history number
!123

# Use the last argument of the previous command
mkdir project
cd !$

# Clear history (careful, you lose your command record)
history -c
```

## Performance / Optimization Notes

- `Ctrl+R` is the fastest way to find an old command. Type part of the command and press Enter to run it.
- Your history is saved to `~/.bash_history`. It loads when you open a new terminal.
- Set `HISTSIZE` and `HISTFILESIZE` in your `.bashrc` to control how many commands are saved.
