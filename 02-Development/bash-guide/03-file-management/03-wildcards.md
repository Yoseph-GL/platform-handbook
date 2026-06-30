# Bash File Management: Wildcards

## Architecture / Rationale

Wildcards (also called glob patterns) match multiple file names in one command. They save you from typing every file name individually.

Common wildcards:
- `*` — matches any number of characters (including zero).
- `?` — matches exactly one character.
- `[abc]` — matches one character from the set.
- `[a-z]` — matches one character in the range.

## Query / Code Blocks

```bash
# List all .txt files
ls *.txt

# List all files starting with "report"
ls report*

# List files with exactly 4-character names
ls ????

# List files ending in .jpg or .png
ls *.{jpg,png}

# List files starting with a, b, or c
ls [a-c]*

# Copy all .log files to a backup folder
cp *.log backup/
```

## Performance / Optimization Notes

- Wildcards are expanded by Bash, not by the command. The command never sees the `*` — it sees the list of matching files.
- Be careful with `*` in `rm` commands. Test with `ls *.pattern` first, then replace `ls` with `rm`.
- Brackets `[...]` match case-sensitive characters. `[A-Z]` and `[a-z]` match different files.
