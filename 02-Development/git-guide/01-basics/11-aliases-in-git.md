# Git Basics: Aliases in Git

## Architecture / Rationale

Git aliases are shortcuts for commands you use often. Instead of typing `git commit`, you can type `git ci`. Aliases save time and reduce typing mistakes.

- Aliases are stored in your Git configuration.
- You can create aliases for any Git command, including complex ones with options.
- Aliases can be global (all projects) or local (one project).

## Query / Code Blocks

```bash
# Create a global alias
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.st status

# Now you can use:
git st      # instead of git status
git co main # instead of git checkout main

# Create an alias with options
git config --global alias.lg "log --oneline --graph --decorate -10"

# Use it:
git lg

# List all your aliases
git config --list | grep alias
```

## Performance / Optimization Notes

- Start with 3-5 aliases for your most-used commands. Too many aliases become hard to remember.
- Common useful aliases: `co` for checkout, `br` for branch, `ci` for commit, `st` for status.
- Shell aliases (in `.bashrc`) and Git aliases serve different purposes. Git aliases only work inside `git` commands.
