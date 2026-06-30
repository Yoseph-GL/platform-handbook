# Git GitHub: Commit Conventions

## Architecture / Rationale

Conventional Commits is a standard format for commit messages. It makes your project history easy to read and lets tools generate changelogs automatically.

The format:
```
<type>(<scope>): <short description>
```

Rules:
- `type` says what kind of change it is (`docs`, `feat`, `fix`, `refactor`, `chore`).
- `scope` says which part of the project changed (`sql`, `bash`, `css`).
- The description starts with a lowercase verb in imperative mood ("add", "fix", "update").
- Keep the first line under 72 characters.

## Query / Code Blocks

```bash
# Good commit messages
git commit -m "docs(sql): add join examples to intermediate level"
git commit -m "feat(bash): create deployment script for production"
git commit -m "fix(css): correct flexbox alignment in navbar"

# Bad commit messages (avoid these)
git commit -m "fixed stuff"
git commit -m "updated some files and made changes"
git commit -m "WIP"

# Multi-line commit for more context
git commit -m "refactor(structure): move legacy scripts to archive" -m "Old scripts were unused and confusing. Archive them for reference but remove from active path."
```

## Performance / Optimization Notes

- Use these types: `docs` (documentation), `feat` (new feature), `fix` (bug fix), `refactor` (structure change), `chore` (maintenance).
- Other useful types: `test` (adding tests), `perf` (performance improvement), `ci` (pipeline changes), `style` (formatting only).
- One commit per logical change. Do not mix a bug fix and a new feature in the same commit.
- Use `git log --oneline` to scan the history. Consistent messages make this output readable.

[[02-good-practices]]
