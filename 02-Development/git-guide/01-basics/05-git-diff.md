# Git Basics: Git Diff

## Architecture / Rationale

`git diff` shows the exact differences between versions of your files. It is the most important tool for reviewing changes before you commit them.

- `git diff` shows unstaged changes (what you changed but have not added yet).
- `git diff --staged` shows staged changes (what will go into the next commit).
- `git diff branch1..branch2` shows differences between two branches.

## Query / Code Blocks

```bash
# See unstaged changes
git diff

# See changes already staged for commit
git diff --staged

# See differences between two commits
git diff commit1 commit2

# See the summary of changes (file names only)
git diff --name-only

# See word-level changes (useful for text)
git diff --word-diff
```

## Performance / Optimization Notes

- Run `git diff --staged` before every commit. It is your last chance to catch mistakes.
- `git diff` uses plus (+) and minus (-) signs. Plus means added, minus means removed.
- Use `git difftool` to open a visual diff tool if you prefer graphical comparisons.
