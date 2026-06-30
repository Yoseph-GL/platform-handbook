# Bash Advanced Commands: Redirections and Pipes

## Architecture / Rationale

Redirections control where command output goes and where input comes from. Pipes connect the output of one command to the input of another.

- `>` — redirect output to a file (overwrites).
- `>>` — redirect output to a file (appends).
- `<` — redirect a file to a command's input.
- `|` — pipe: send output of command A to input of command B.

## Query / Code Blocks

```bash
# Save command output to a file (overwrite)
ls -l > listing.txt

# Append output to a file
echo "new line" >> log.txt

# Read input from a file
sort < unsorted.txt

# Pipe: list files, then search for ".txt"
ls -l | grep ".txt"

# Pipe chain: find all .txt files, count them
ls | grep ".txt" | wc -l

# Redirect errors to a file (2>)
ls nonexistent 2> errors.log

# Redirect both output and errors to the same file
ls existing nonexistent &> all-output.log
```

## Performance / Optimization Notes

- Pipes avoid creating temporary files. `cmd1 | cmd2` is cleaner and faster than `cmd1 > tmp; cmd2 < tmp; rm tmp`.
- `>` overwrites without asking. Use `>>` if you want to keep the old content.
- File descriptors: `1` is standard output, `2` is standard error. `2>&1` merges them.
