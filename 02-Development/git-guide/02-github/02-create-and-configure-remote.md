# Git GitHub: Create and Configure a Remote Repository

## Architecture / Rationale

A remote repository is a copy of your Git project stored on a server (like GitHub). You connect your local repository to the remote so you can push and pull changes.

- `git remote add` links your local repository to a remote URL.
- `origin` is the conventional name for the main remote.
- Remotes can use HTTPS or SSH URLs.

## Query / Code Blocks

```bash
# Add a remote (after creating the repo on GitHub)
git remote add origin https://github.com/username/repo.git

# Check your remotes
git remote -v

# Change the remote URL
git remote set-url origin git@github.com:username/repo.git

# Remove a remote
git remote remove origin
```

## Performance / Optimization Notes

- SSH keys are more secure than HTTPS and do not require entering your password every time.
- Use the exact URL GitHub gives you after creating the repository. Copy and paste it.
- A repository can have multiple remotes. `origin` is the default, but you can add `upstream` for the source project when working with forks.
