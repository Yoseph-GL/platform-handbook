# Git Basics: Restore, Checkout and More

## Architecture / Rationale

Git lets you undo changes before they become permanent. You can restore a file to its last committed state or switch to a different version of your project.

- `git restore` discards changes in your working directory.
- `git checkout` switches branches or restores files (older command, still common).
- `git restore --staged` unstages files without losing the changes.

## Query / Code Blocks

```bash
# Discard changes to a file (go back to last commit)
git restore file.txt

# Unstage a file (keep the changes, just remove from staging)
git restore --staged file.txt

# Old way: same as restore (checkout is still widely used)
git checkout -- file.txt

# Switch to a different branch
git checkout branch-name
```

## Performance / Optimization Notes

- `git restore` is the modern command (Git 2.23+). `git checkout` does the same thing but is older and does more than one job.
- Changes you discard with `restore` are gone forever. Make sure you do not need them before running the command.
- Restore only works on files Git is tracking. New files that were never committed cannot be restored.
