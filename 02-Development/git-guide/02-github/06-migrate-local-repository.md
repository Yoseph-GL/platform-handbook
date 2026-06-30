# Git GitHub: Migrate a Local Repository

## Architecture / Rationale

You can take an existing local Git repository and upload it to GitHub. This is how you turn a project you started on your computer into a shared, backed-up repository.

Steps:
1. Create an empty repository on GitHub (do not add a README or .gitignore).
2. Add the remote URL to your local repository.
3. Push your branch to GitHub.

## Query / Code Blocks

```bash
# Create an empty repo on GitHub (no README, no .gitignore)

# In your local repository:
git remote add origin https://github.com/username/repo.git

# Rename your branch to main (if it's still "master")
git branch -M main

# Push and set upstream
git push -u origin main

# Your local repo is now connected to GitHub
```

## Performance / Optimization Notes

- Make sure the GitHub repository is empty. Pushing to a repo that already has commits causes conflicts.
- The `-M` flag renames the branch even if `main` already exists. Use lowercase `-m` if you are not sure.
- After migrating, check `git remote -v` to confirm the URL is correct.
