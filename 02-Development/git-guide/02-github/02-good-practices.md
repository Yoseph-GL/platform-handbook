# Git GitHub: Good Practices

## Architecture / Rationale

Good Git habits prevent mistakes and keep the project history clean. These rules apply every time you commit code.

Core rules:
- Commit often. Small commits are easier to understand and undo than large ones.
- Write meaningful messages. The commit message should explain why the change was made.
- Pull before you push. Always get the latest changes from the remote before pushing yours.

## Query / Code Blocks

```bash
# Check status before committing
git status

# Stage specific files, not everything
git add path/to/file.txt

# Review what you are about to commit
git diff --staged

# Pull latest changes before pushing
git pull --rebase origin main

# Push your work
git push origin main
```

## Performance / Optimization Notes

- Never use `git add .` without checking `git status` first. It can add files you did not intend to commit.
- Use `git pull --rebase` instead of `git pull`. It keeps the history linear and easier to read.
- Delete branches after they are merged. Old branches clutter the repository and confuse the team.
- Write commit messages in English. It is the standard language for open-source projects.

[[01-commit-conventions]]
