# Bash First Steps: Navigation Commands

## Architecture / Rationale

Navigation commands move you between folders. The file system is a tree. You start somewhere and use `cd` to move around.

- `cd` (Change Directory) — moves you to a different folder.
- `cd ..` — goes up one level (to the parent folder).
- `cd ~` or `cd` alone — goes to your home folder.
- `cd -` — goes back to the last folder you were in.

## Query / Code Blocks

```bash
# Go to a specific folder
cd /home/username/Documents

# Go up one level
cd ..

# Go to your home folder
cd ~

# Go back to where you just were
cd -
```

## Performance / Optimization Notes

- Tab completion saves time. Type the first letters of a folder name and press Tab. Bash completes it.
- `cd -` is the fastest way to switch between two folders you are working in.
- Use `pushd` and `popd` if you need to jump between many folders. They keep a stack of visited directories.
