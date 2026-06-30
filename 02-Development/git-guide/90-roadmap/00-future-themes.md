# Git Roadmap: Future Themes

## Architecture / Rationale

This roadmap keeps the guide scalable without mixing advanced topics into the foundational levels.

Planned progression:
1. **Branching and Merging**: feature branches, merge vs rebase, conflict resolution.
2. **Git Internals**: objects, trees, commits, and the `.git` folder structure.
3. **Advanced GitHub**: Actions, CI/CD pipelines, protected branches, and code review.
4. **Git Hooks**: pre-commit, pre-push, and automated checks.
5. **Undoing Changes**: reset, revert, cherry-pick, and interactive rebase.
6. **Git Workflows**: GitFlow, trunk-based development, and release strategies.

## Query / Code Blocks

```bash
# Example placeholder for upcoming branching module
git checkout -b feature/new-feature
# Make changes...
git commit -m "feat: add new feature"
git checkout main
git merge feature/new-feature
```

## Performance / Optimization Notes

- Keep advanced topics isolated by level to preserve entry-level readability.
- Promote topics from the roadmap to active modules only after studying them.
- Git has many commands. You do not need to learn them all at once.
