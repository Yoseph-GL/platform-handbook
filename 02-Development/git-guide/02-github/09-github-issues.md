# Git GitHub: GitHub Issues

## Architecture / Rationale

Issues are GitHub's way of tracking tasks, bugs, and feature requests. They are the starting point for most work on a project.

- Issues can have labels, assignees, and milestones.
- You can link issues to pull requests.
- Issues support Markdown, code blocks, and images.

## Query / Code Blocks

```bash
# Issues are managed on GitHub's web interface

# Typical issue workflow:
# 1. Open the repository, go to "Issues", click "New issue"
# 2. Write a descriptive title and detailed body
# 3. Add labels (bug, enhancement, documentation)
# 4. Assign someone (or yourself)
# 5. When work starts, create a branch and reference the issue in commits
git commit -m "fix(ui): correct button alignment (#42)"

# 6. When the PR merges, the issue closes automatically with "Closes #42"
```

## Performance / Optimization Notes

- Write clear issue titles. "Login button is invisible on mobile" is better than "bug".
- Include steps to reproduce bugs. The clearer the report, the faster someone can fix it.
- Use labels to organize issues. Even on personal projects, labels help you prioritize.
