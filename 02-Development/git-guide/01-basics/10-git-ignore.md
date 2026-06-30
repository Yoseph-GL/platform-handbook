# Git Basics: Git Ignore

## Architecture / Rationale

A `.gitignore` file tells Git which files to ignore. Temporary files, build outputs, and secrets should never be committed to the repository.

- `.gitignore` is a plain text file at the root of your project.
- Patterns can match file names, folders, or extensions.
- Files already tracked by Git are not affected by `.gitignore`. You must untrack them first.

## Query / Code Blocks

```bash
# Example .gitignore file
# node_modules/        — ignore a folder
# .env                 — ignore a specific file
# *.log                — ignore all files ending in .log
# !important.log       — but keep this one
# build/               — ignore the build output

# Check which files are being ignored
git status --ignored

# If a file was committed before being added to .gitignore:
git rm --cached file.log
```

## Performance / Optimization Notes

- Create a `.gitignore` file before your first commit. Adding it later is possible but more work.
- GitHub provides `.gitignore` templates for most languages and frameworks. Start with one that matches your project.
- Sensitive files like `.env` and API keys must always be in `.gitignore`. Once pushed, they are in the history forever.
