# Git GitHub: Forks and Contributions

## Architecture / Rationale

A fork is your own copy of someone else's repository. It lets you make changes without affecting the original project. When your changes are ready, you propose them back with a pull request.

- Forking happens on GitHub (click the Fork button).
- You clone your fork, make changes, and push to your fork.
- A pull request asks the original project to accept your changes.

## Query / Code Blocks

```bash
# 1. Fork the repository on GitHub (click "Fork")

# 2. Clone your fork (not the original)
git clone https://github.com/your-username/repo.git

# 3. Add the original as "upstream" to stay updated
git remote add upstream https://github.com/original-owner/repo.git

# 4. Create a branch, make changes, commit, push
git switch -c my-contribution
# ... make changes ...
git add .
git commit -m "Add new feature"
git push -u origin my-contribution

# 5. Open a Pull Request on GitHub
```

## Performance / Optimization Notes

- Always create a branch for your contribution. Never work directly on `main`.
- Keep your fork updated: `git fetch upstream && git merge upstream/main`.
- One pull request should solve one problem. Do not mix unrelated changes in the same PR.
