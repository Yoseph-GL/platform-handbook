# Bash First Steps: Absolute and Relative Paths

## Architecture / Rationale

A path tells the shell where a file or folder is. There are two kinds: absolute paths start from the root, relative paths start from where you are.

- **Absolute path**: starts with `/`. It works from anywhere. Example: `/home/user/Documents/report.txt`.
- **Relative path**: starts from the current folder. Example: `Documents/report.txt` or `../photos/pic.jpg`.
- `.` means the current folder. `..` means the parent folder.

## Query / Code Blocks

```bash
# Absolute path: works from anywhere
ls /usr/bin

# Relative path: depends on where you are
ls Documents

# Go to a sibling folder (same parent)
cd ../Downloads

# Current folder (rarely needed but good to know)
ls ./

# Home folder shorthand
ls ~/Documents
```

## Performance / Optimization Notes

- Use relative paths for files inside your project. They keep scripts portable.
- Absolute paths are safer in scripts because they do not depend on where the script runs from.
- `~` is always your home folder. Use it as a shortcut instead of `/home/yourname`.
