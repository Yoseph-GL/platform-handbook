# Git GitHub: Commit Conventions

## Architecture / Rationale

Conventional Commits is a standard format for commit messages. It makes your project history readable and lets tools generate changelogs automatically.

The format:
```
<type>(<scope>): <short description>
```

Rules:
- `type` says what kind of change it is.
- `scope` says which part of the project changed (optional but recommended).
- The description starts with a lowercase verb and is under 72 characters.
- Each commit does one thing. Do not mix a bug fix and a new feature in the same commit.

## Query / Code Blocks

```bash
# Primary commit types
# docs     — documentation and guides
# feat     — new feature or script
# fix      — bug fix or error correction
# refactor — structure changes without changing functionality
# chore    — maintenance (gitignore, license, config)

# Extended types
# test     — adding or updating tests
# perf     — performance improvements
# ci       — pipeline and workflow changes
# style    — formatting only (no logic change)
# revert   — undo a previous commit

# Good commit messages
git commit -m "docs(sql): add join examples to intermediate level"
git commit -m "feat(bash): create deployment script for production"
git commit -m "fix(css): correct flexbox alignment in navbar"

# Multi-line commit for more context
git commit -m "refactor(struct): move legacy scripts to archive" \
           -m "Old scripts were unused. Archive for reference but remove from active path."

# Bad commit messages (avoid these)
git commit -m "fixed stuff"
git commit -m "updated files"
git commit -m "WIP"

# Check the history
git log --oneline --graph --decorate -n 10
```

## Performance / Optimization Notes

- Follow the format for every commit. Consistent messages make `git log --oneline` a joy to read.
- Stage changes carefully. Use `git add` on specific files, not `git add .` without checking first.
- The scope is optional but helpful in projects with many modules (like this one).
- Write commit messages in English. It is the standard language for open-source collaboration.

[[10-good-practices]]
