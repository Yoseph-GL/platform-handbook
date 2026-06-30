# Git GitHub: Good Practices in Git

## Architecture / Rationale

Good Git habits prevent mistakes and keep the project history clean. These rules apply whether you work alone or in a team.

Core rules:
- Commit often. Small commits are easier to understand and undo than large ones.
- Write meaningful messages. Use the Conventional Commits format: `<type>(<scope>): <description>`.
- Pull before you push. Always get the latest changes from the remote before pushing yours.
- One commit per logical change. Do not mix a bug fix and a new feature in the same commit.

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

# Good commit messages (Conventional Commits)
git commit -m "docs(git): add branching examples"
git commit -m "feat(bash): create deployment script"
git commit -m "fix(css): correct flexbox alignment in navbar"

# Bad commit messages (avoid these)
git commit -m "fixed stuff"
git commit -m "WIP"
```

## Performance / Optimization Notes

- Never use `git add .` without checking `git status` first. It can add files you never meant to commit.
- Use `git pull --rebase` instead of `git pull`. It keeps the history linear and easier to read.
- Delete branches after they are merged. Old branches clutter the repository and confuse the team.
- Write commit messages in English. It is the standard language for open-source projects.
- For the full commit message standard, see [[12-commit-conventions]].

[[11-next-steps]]
[[12-commit-conventions]]
