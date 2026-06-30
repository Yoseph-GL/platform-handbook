# Git Basics: What is Git?

## Architecture / Rationale

Git is a version control system. It tracks changes to your files over time. You can go back to any previous version, see who changed what, and work on multiple features in parallel without losing anything.

Key facts:
- Git is distributed. Every developer has the full history on their computer.
- Git stores snapshots, not differences. Each commit is a complete picture of your project at that moment.
- Git works offline. You only need an internet connection to share changes with others.

## Query / Code Blocks

```bash
# Check if Git is installed
git --version

# Create a new Git repository
git init

# Your first Git repository is ready
```

## Performance / Optimization Notes

- Git is fast because it stores everything locally. Browsing history and switching branches happens in milliseconds.
- A Git repository is just a hidden `.git` folder. The rest of your project folder is your normal working directory.
- Learn Git from the command line first. GUI tools are helpful later but hide what Git actually does.
