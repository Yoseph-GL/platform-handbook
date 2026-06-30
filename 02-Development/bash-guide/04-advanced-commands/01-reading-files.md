# Bash Advanced Commands: Reading Files

## Architecture / Rationale

Bash has several commands for reading files. Each one works best for a specific situation.

- `cat` (concatenate) — prints the whole file at once. Best for short files.
- `less` — opens a file for scrolling. Press `q` to quit, `/` to search. Best for long files.
- `more` — an older, simpler version of `less`. `less` is better (less is more).

## Query / Code Blocks

```bash
# Print a short file to the terminal
cat notes.txt

# Print multiple files one after another
cat file1.txt file2.txt

# View a long file with scrolling
less /var/log/syslog

# Inside less: /search-term, n for next, q to quit

# Number all lines when printing
cat -n script.sh
```

## Performance / Optimization Notes

- Never use `cat` on a file larger than a few pages. It floods your terminal. Use `less` instead.
- `less` does not load the whole file into memory. It is fast even on multi-gigabyte files.
- `cat` is short for "concatenate". Its main job is joining files, but it is most often used to print one.
