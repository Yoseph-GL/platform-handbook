# Bash Level 4: Advanced Commands

## Architecture / Rationale

This level covers commands that process and combine data. You learn to read files, search for text, redirect output, and work with environment variables.

Scope:
- Reading files with `cat`, `less`, `head`, and `tail`.
- Searching with `grep` and counting with `wc`.
- Redirecting output and chaining commands with pipes.
- Environment variables and the `export` command.

## Query / Code Blocks

```bash
# Module pages
# [[01-reading-files]]
# [[02-head-and-tail]]
# [[03-search-and-count]]
# [[04-grep-basics]]
# [[05-redirections-and-pipes]]
# [[06-environment-variables]]
# [[07-exercises-advanced-commands]]
```

## Performance / Optimization Notes

- Pipes connect commands without creating temporary files. They are the core of the Unix philosophy.
- Environment variables configure your shell and programs. Learn the common ones before creating your own.
