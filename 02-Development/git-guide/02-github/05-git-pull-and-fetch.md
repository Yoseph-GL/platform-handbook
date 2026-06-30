# Git GitHub: Git Pull and Git Fetch

## Architecture / Rationale

`git pull` and `git fetch` download changes from the remote repository. The difference is what happens after downloading.

- `git fetch` downloads changes but does not apply them. It is safe — it never modifies your working directory.
- `git pull` downloads and immediately merges the changes into your current branch.
- `git pull` is shorthand for `git fetch` followed by `git merge`.

## Query / Code Blocks

```bash
# Fetch all changes from origin (safe, no merge)
git fetch

# Fetch from a specific remote
git fetch origin

# Pull: fetch and merge in one step
git pull

# Pull with rebase (cleaner history)
git pull --rebase

# See what changed on the remote before pulling
git fetch
git log HEAD..origin/main --oneline
```

## Performance / Optimization Notes

- Use `git fetch` to check what changed before merging. It lets you review without affecting your work.
- `git pull --rebase` keeps the history cleaner than `git pull` (which creates merge commits).
- Run `git fetch` regularly. It updates your local copy of the remote branches without touching your work.
