# Git Basics: First Steps in Git

## Architecture / Rationale

The basic Git workflow has three steps: make changes, stage them, and commit. This is the cycle you repeat hundreds of times a day.

- `git status` shows what has changed and what is staged.
- `git add` stages files for the next commit.
- `git commit` saves the staged changes to the repository history.

## Query / Code Blocks

```bash
# Check what changed
git status

# Stage a specific file
git add index.html

# Stage all changed files
git add .

# Commit with a message
git commit -m "Add homepage structure"

# Shortcut: stage all tracked files and commit in one step
git commit -am "Update existing files"
```

## Performance / Optimization Notes

- Always run `git status` before `git add`. It prevents accidentally staging files you did not mean to change.
- Write commit messages in present tense: "Add feature" not "Added feature".
- Each commit should be one logical change. If you cannot describe it in one short sentence, split it into two commits.
