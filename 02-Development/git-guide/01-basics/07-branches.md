# Git Basics: Branches

## Architecture / Rationale

A branch is an independent line of development. You can work on a new feature in a branch without affecting the main code. When the feature is ready, you merge it back.

- `git branch` lists, creates, and deletes branches.
- `git switch` changes which branch you are working on.
- `main` is the default primary branch (previously called `master`).

## Query / Code Blocks

```bash
# List all branches (* marks the current one)
git branch

# Create a new branch
git branch feature-login

# Switch to a branch
git switch feature-login
# or: git checkout feature-login

# Create and switch in one command
git switch -c feature-signup

# Delete a merged branch
git branch -d feature-login

# List branches merged into main
git branch --merged
```

## Performance / Optimization Notes

- Create a branch for every feature or bug fix. Branches are fast and cheap in Git.
- Delete branches after merging. Old branches confuse you and your team.
- Name branches with a clear pattern: `feature/name`, `bugfix/description`, `experiment/idea`.
