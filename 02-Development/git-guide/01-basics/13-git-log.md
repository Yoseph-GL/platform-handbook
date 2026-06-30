# Git Basics: Git Log

## Architecture / Rationale

`git log` shows the commit history of your repository. It is how you browse the past, find specific changes, and understand the evolution of a project.

- `git log` shows commits in reverse chronological order (newest first).
- Many formatting options let you customize the output.
- You can filter by author, date, file, or message content.

## Query / Code Blocks

```bash
# Basic log: full details of every commit
git log

# Compact one-line format
git log --oneline

# Show branches and merges as a graph
git log --oneline --graph --decorate

# Show commits by a specific author
git log --author="Your Name"

# Show commits that changed a specific file
git log -- path/to/file.txt

# Show the last 5 commits
git log -5

# Show commits between two dates
git log --since="2026-01-01" --until="2026-06-30"
```

## Performance / Optimization Notes

- `git log --oneline --graph --decorate` is the most useful combination. Many people alias it to `git lg`.
- Use `git log -- file.txt` to find out when and why a specific file was changed.
- `git log -S "function name"` searches for commits that added or removed a specific string.
