# Bash Advanced Commands: Head and Tail

## Architecture / Rationale

`head` and `tail` show the beginning or the end of a file. They are useful for previewing files and monitoring logs.

- `head` — shows the first 10 lines (by default). Use `-n` to change the number.
- `tail` — shows the last 10 lines. Use `-n` to change the number.
- `tail -f` — follows a file. It prints new lines as they are added. Press Ctrl+C to stop.

## Query / Code Blocks

```bash
# First 10 lines of a file
head file.txt

# First 5 lines
head -n 5 file.txt

# Last 10 lines
tail file.txt

# Last 20 lines
tail -n 20 file.txt

# Follow a log file in real time
tail -f /var/log/syslog

# Skip the first line (start from line 2)
tail -n +2 file.txt
```

## Performance / Optimization Notes

- `tail -f` is essential for watching log files while debugging. It updates automatically.
- `head` is fast even on huge files because it stops reading after the requested number of lines.
- Use `head` to preview a file before opening it fully. It confirms you have the right file.
