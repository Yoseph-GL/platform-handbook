# Bash File Management: Advanced Listings

## Architecture / Rationale

`ls` has many options that show more information about files. Learning the flags turns `ls` from a simple lister into a powerful inspection tool.

Useful `ls` flags:
- `-l` — long format (permissions, owner, size, date).
- `-a` — show hidden files (files starting with `.`).
- `-h` — human-readable sizes (1K, 234M, 2G).
- `-t` — sort by modification time, newest first.
- `-r` — reverse the sort order.
- `-R` — list folders recursively.

## Query / Code Blocks

```bash
# Long format with human-readable sizes
ls -lh

# Show all files, including hidden ones
ls -la

# Sort by time, newest first
ls -lt

# Sort by size, largest first
ls -lS

# Reverse sort (oldest first)
ls -ltr

# Recursive listing (everything inside subfolders)
ls -R
```

## Performance / Optimization Notes

- `ls -la` is the most common combination. Many people alias it to `ll`.
- Hidden files (starting with `.`) are hidden by convention, not by security. `ls -a` reveals them.
- `ls -ltr` shows the most recently changed files at the bottom. Useful in folders with many files.
