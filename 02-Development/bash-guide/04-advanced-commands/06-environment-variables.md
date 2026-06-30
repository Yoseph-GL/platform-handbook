# Bash Advanced Commands: Environment Variables

## Architecture / Rationale

Environment variables store configuration values that programs can read. They control how your shell and many programs behave.

Common variables:
- `$HOME` — your home folder path.
- `$PATH` — folders where Bash looks for commands.
- `$USER` — your username.
- `$SHELL` — your current shell.
- `$PWD` — your current working directory.

## Query / Code Blocks

```bash
# Show one variable
echo $HOME

# Show all environment variables
env

# Show a specific variable
echo $PATH

# Set a variable for this session
MY_VAR="hello"
echo $MY_VAR

# Export: make the variable available to child processes
export MY_VAR="hello"

# Add a folder to PATH (temporary)
export PATH="$PATH:/home/user/bin"

# Common: set your default editor
export EDITOR=nano
```

## Performance / Optimization Notes

- `$PATH` is the most important environment variable. If a command is "not found", the problem is usually in `$PATH`.
- Variables without `export` are only visible in the current shell. Use `export` when child processes need them.
- Permanent variables go in `~/.bashrc` or `~/.profile`, not in the terminal. Add them once, they load on every session.
