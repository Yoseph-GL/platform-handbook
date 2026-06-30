# Bash First Steps: Which and Type

## Architecture / Rationale

`which` and `type` tell you where a command lives and what kind of command it is. They help you understand what runs when you type a name.

- `which` — shows the full path to a program. Example: `which ls` → `/usr/bin/ls`.
- `type` — tells you if the command is a program, an alias, or a Bash built-in.
- A command can be in multiple forms. Bash uses the first one it finds in the search order.

## Query / Code Blocks

```bash
# Where is the ls program?
which ls

# Where is python?
which python3

# What kind of command is echo?
type echo

# What kind of command is ls?
type ls

# Show all possible matches for a command name
type -a echo
```

## Performance / Optimization Notes

- Use `which` to find where a program is installed. Useful when a command is not working and you need to check the path.
- `type` is a Bash built-in. It knows about aliases and functions. `which` only knows about programs.
- If a command behaves differently than you expect, run `type -a <command>` to see which version is running.
