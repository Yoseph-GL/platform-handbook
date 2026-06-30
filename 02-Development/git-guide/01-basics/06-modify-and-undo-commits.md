# Git Basics: Modify and Undo Commits

## Architecture / Rationale

Mistakes happen. Git gives you several ways to fix commits before and after they are made. The right command depends on whether the commit is still local or already shared.

- `git commit --amend` changes the last commit (message or content).
- `git reset` moves the branch pointer backward, undoing commits.
- `git revert` creates a new commit that undoes a previous one (safe for shared branches).

## Query / Code Blocks

```bash
# Fix the message of the last commit
git commit --amend -m "New, better message"

# Add a forgotten file to the last commit
git add forgotten-file.txt
git commit --amend --no-edit

# Undo the last commit but keep the changes (soft reset)
git reset --soft HEAD~1

# Undo the last commit and discard changes (hard reset — careful!)
git reset --hard HEAD~1

# Safe undo: create a new commit that reverses an old one
git revert abc123
```

## Performance / Optimization Notes

- `--amend` only works on the most recent commit. You cannot amend commits further back.
- Never `reset --hard` on commits you have already pushed. Other people might have based work on them.
- `revert` is always safe. It adds a new commit instead of rewriting history.
