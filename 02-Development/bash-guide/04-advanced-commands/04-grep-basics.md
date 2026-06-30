# Bash Advanced Commands: Grep Basics

## Architecture / Rationale

`grep` (Global Regular Expression Print) is the most important text-searching tool in Unix. It finds lines that match a pattern and prints them.

Common `grep` flags:
- `-i` — ignore case (uppercase and lowercase are the same).
- `-v` — invert: show lines that do NOT match.
- `-n` — show line numbers.
- `-c` — count matching lines instead of printing them.
- `-r` — search recursively through folders.

## Query / Code Blocks

```bash
# Find lines containing "error"
grep "error" app.log

# Ignore case: find Error, ERROR, error
grep -i "error" app.log

# Show lines that do NOT contain "debug"
grep -v "debug" app.log

# Show line numbers with matches
grep -n "TODO" script.sh

# Count how many lines match
grep -c "success" app.log

# Search all files in a folder recursively
grep -r "function" src/

# Combine flags: case-insensitive search with line numbers
grep -in "error" app.log
```

## Performance / Optimization Notes

- `grep` processes files line by line. It handles files larger than your RAM without problems.
- The pattern you give `grep` is a regular expression. Start with plain text, learn regex patterns later.
- `grep -v` is useful for filtering out noise. Use it to remove debug lines or comments from output.
