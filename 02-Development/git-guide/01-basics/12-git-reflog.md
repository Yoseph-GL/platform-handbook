# Git Basics: Git Reflog

## Architecture / Rationale

The reflog records every time the tip of a branch changes. Even if you delete a branch or reset commits, the reflog remembers. It is your safety net when things go wrong.

- `git reflog` shows the history of where your HEAD has been.
- Entries expire after 90 days by default.
- You can recover lost commits by finding them in the reflog and resetting to them.

## Query / Code Blocks

```bash
# View the reflog
git reflog

# Output example:
# abc1234 HEAD@{0}: commit: Add login page
# def5678 HEAD@{1}: reset: moving to HEAD~1
# ghi9012 HEAD@{2}: merge feature-branch: Merge made by ort

# Recover a lost commit
git reset --hard HEAD@{2}

# Recover a deleted branch
git checkout -b recovered-branch HEAD@{5}
```

## Performance / Optimization Notes

- The reflog is your undo system for Git itself. If you lose work, check the reflog first.
- Reflog entries are local. They are never pushed to the remote repository.
- After 90 days, old reflog entries are cleaned up. Recover important lost work quickly.
