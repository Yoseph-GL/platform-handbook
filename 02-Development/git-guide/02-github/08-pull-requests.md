# Git GitHub: Pull Requests

## Architecture / Rationale

A Pull Request (PR) is a request to merge your changes into another branch. It is the core of code review and collaboration on GitHub.

- PRs let others review your code before it goes into the main branch.
- You can discuss changes, add comments, and request specific reviewers.
- Automated checks (tests, linting) can run on PRs to catch problems early.

## Query / Code Blocks

```bash
# Pull requests are created on the GitHub web interface

# Typical PR workflow:
# 1. Push your branch to GitHub
git push -u origin feature-branch

# 2. Open GitHub, go to the repository, click "Pull requests"
# 3. Click "New pull request"
# 4. Select base branch (where to merge) and compare branch (your changes)
# 5. Write a clear title and description
# 6. Request reviewers
# 7. Address feedback, make changes, push again (the PR updates automatically)
# 8. When approved, merge the PR
```

## Performance / Optimization Notes

- Write a clear PR title and description. Explain what you changed and why.
- Keep PRs small. A PR with 50 lines is easy to review. A PR with 5000 lines is not.
- Link related issues in the PR description with `Closes #123` to auto-close them when merged.
