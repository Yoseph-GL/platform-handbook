# Bash Advanced Commands: Search and Count

## Architecture / Rationale

`grep` searches for text patterns in files. `wc` counts lines, words, and characters. Together they answer most questions about file contents.

- `grep` — searches for lines matching a pattern.
- `wc` (Word Count) — counts lines (`-l`), words (`-w`), or characters (`-c`).
- Combine them: `grep pattern file | wc -l` counts matching lines.

## Query / Code Blocks

```bash
# Search for a word in a file
grep "error" log.txt

# Search case-insensitive
grep -i "error" log.txt

# Count lines in a file
wc -l file.txt

# Count words
wc -w file.txt

# Count how many lines contain "error"
grep "error" log.txt | wc -l

# Search in all .txt files
grep "todo" *.txt
```

## Performance / Optimization Notes

- `grep` is one of the fastest text search tools available. It is optimized over decades of use.
- Use `grep -r` to search recursively through folders. It finds matches in every file.
- `wc -l` is the standard way to count output lines in pipelines.
