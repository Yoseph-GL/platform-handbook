# Git GitHub: Git Push

## Architecture / Rationale

`git push` sends your local commits to the remote repository. It is how you share your work with others and back it up to GitHub.

- Push after committing. Your commits are only local until you push.
- `git push origin main` pushes the `main` branch to the `origin` remote.
- The first push of a new branch needs `-u` to set the upstream tracking.

## Query / Code Blocks

```bash
# Push the current branch to origin
git push

# Push a specific branch
git push origin main

# First push: set upstream and push in one command
git push -u origin feature-login

# Force push (dangerous — overwrites remote history)
git push --force
# Safer alternative:
git push --force-with-lease
```

## Performance / Optimization Notes

- Push often. It backs up your work and lets others see your progress.
- Never force-push to `main` or any shared branch. It destroys other people's work.
- If your push is rejected, pull first (`git pull`), resolve any conflicts, then push again.
