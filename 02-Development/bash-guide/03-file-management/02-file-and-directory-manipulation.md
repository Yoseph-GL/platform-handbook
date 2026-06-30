# Bash File Management: File and Directory Manipulation

## Architecture / Rationale

This note expands on the basic commands from Level 2. You learn the safer and more powerful ways to work with files and folders.

Key commands with useful flags:
- `mkdir -p` — create nested folders in one command.
- `cp -r` — copy folders and their contents.
- `mv -i` — ask before overwriting.
- `rm -rf` — force-delete a folder. Extremely dangerous. Double-check before using.

## Query / Code Blocks

```bash
# Create nested folders in one step
mkdir -p project/src/components

# Copy a folder and everything inside
cp -r project project-backup

# Move with confirmation before overwriting
mv -i file.txt destination/

# Safe delete: ask before each file
rm -i *.txt

# ⚠️ Dangerous: force-delete without asking
# rm -rf old-project
```

## Performance / Optimization Notes

- Always use `-i` (interactive) with `rm` and `mv` until you are confident. It asks before overwriting or deleting.
- `mkdir -p` is the safest command in Bash. It creates all missing folders and does nothing if they already exist.
- There is no undo in Bash. Consider using `mv` to a "trash" folder instead of `rm` for important files.
