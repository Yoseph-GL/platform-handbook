# Git Basics: Merging Branches

## Architecture / Rationale

Merging combines the work from two branches into one. When your feature is done, you merge its branch into `main`. Git automatically combines the changes when there are no conflicts.

- `git merge` brings changes from another branch into your current branch.
- A fast-forward merge happens when the target branch has no new commits.
- A merge commit is created when both branches have diverged.

## Query / Code Blocks

```bash
# Switch to the branch you want to merge into (usually main)
git switch main

# Merge the feature branch into main
git merge feature-login

# Fast-forward example: main hasn't changed, just moves the pointer
# Merge commit example: both branches changed, Git creates a new commit

# List merged and unmerged branches
git branch --merged
git branch --no-merged
```

## Performance / Optimization Notes

- Always switch to the target branch (usually `main`) before merging. You merge into the current branch.
- Update both branches before merging: `git pull` on main, then `git merge` the feature.
- Delete the feature branch after a successful merge. It keeps your branch list clean.
