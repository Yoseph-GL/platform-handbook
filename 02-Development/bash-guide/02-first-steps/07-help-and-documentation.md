# Bash First Steps: Help and Documentation

## Architecture / Rationale

You do not need to memorize every command. Bash has built-in help systems. Learning to read documentation is more important than memorizing flags.

Help tools:
- `man <command>` — the full manual page. Press `q` to exit.
- `<command> --help` — a short summary of options.
- `help <builtin>` — help for Bash built-in commands (like `cd`, `echo`).
- `info <command>` — a more detailed manual (rarely needed).

## Query / Code Blocks

```bash
# Full manual for ls
man ls

# Quick help summary
ls --help

# Help for a Bash built-in (cd is built into Bash, not a separate program)
help cd

# Search the manual pages by keyword
man -k keyword
```

## Performance / Optimization Notes

- Start with `--help` for a quick reminder. Use `man` when you need the full details.
- Inside `man`, press `/` to search for a keyword, then `n` for the next match.
- The `man` pages are the source of truth. If a tutorial says something different, trust `man`.
