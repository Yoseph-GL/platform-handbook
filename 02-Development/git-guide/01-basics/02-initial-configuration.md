# Git Basics: Initial Configuration

## Architecture / Rationale

Before using Git, you tell it who you are. Your name and email are attached to every commit you make. This information becomes part of the project history forever.

- `git config` sets your identity and preferences.
- Global settings apply to all repositories on your computer.
- Local settings apply only to the current repository.

## Query / Code Blocks

```bash
# Set your name and email (global, for all projects)
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"

# Check your current configuration
git config --list

# Set the default branch name (recommended: main)
git config --global init.defaultBranch main
```

## Performance / Optimization Notes

- Use a real email address. It is public in open-source projects and how others can contact you about your code.
- Set `init.defaultBranch` to `main` once and forget about it. New repositories will use this name automatically.
- Configuration is stored in `~/.gitconfig`. You can edit that file directly instead of running commands.
