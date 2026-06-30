# Git Basics: Merge Conflicts

## Architecture / Rationale

A merge conflict happens when two branches changed the same part of the same file. Git cannot decide which version to keep, so it asks you to resolve the conflict manually.

- Conflicts are normal. They are not errors, just decisions Git needs you to make.
- Git marks the conflicting sections with `<<<<<<<`, `=======`, and `>>>>>>>`.
- After resolving, you stage the file and complete the merge with a commit.

## Query / Code Blocks

```bash
# When a conflict happens, Git tells you which files are affected
git status

# Open the file and look for conflict markers:
# <<<<<<< HEAD
# your changes
# =======
# changes from the other branch
# >>>>>>> feature-branch

# After editing, mark the conflict as resolved
git add resolved-file.txt

# Complete the merge
git commit -m "Merge feature-branch, resolve conflict in main.py"

# Cancel a merge in progress if you need to start over
git merge --abort
```

## Performance / Optimization Notes

- Pull the latest changes often. Conflicts are smaller and easier to resolve when branches are not far apart.
- Use `git merge --abort` to undo a failed merge and return to a clean state.
- A visual merge tool (like VS Code's built-in resolver) makes conflicts much easier to handle.
