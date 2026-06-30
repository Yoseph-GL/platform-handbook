# Git GitHub: Git Clone

## Architecture / Rationale

`git clone` downloads a complete copy of a remote repository to your computer. It includes the full history, all branches, and automatically sets up the `origin` remote.

- Clone when you want to start working on an existing project.
- The URL comes from the GitHub repository page (green "Code" button).
- Cloning is different from downloading a ZIP. A clone includes the Git history.

## Query / Code Blocks

```bash
# Clone a public repository
git clone https://github.com/username/repo.git

# Clone into a specific folder
git clone https://github.com/username/repo.git my-folder

# Clone a specific branch
git clone -b develop https://github.com/username/repo.git
```

## Performance / Optimization Notes

- Always clone, never download the ZIP. The ZIP file does not include the Git history.
- After cloning, run `git status` to confirm everything is clean before starting work.
- Large repositories take time to clone. Use `--depth 1` for a shallow clone if you only need the latest version.
