# Bash First Steps: Other Basic Commands

## Architecture / Rationale

Beyond navigation, a few commands help you look at and create files and folders. These are the building blocks of daily terminal work.

- `mkdir` (Make Directory) — creates a new folder.
- `touch` — creates an empty file or updates the timestamp of an existing one.
- `cp` (Copy) — copies a file or folder.
- `mv` (Move) — moves or renames a file or folder.
- `rm` (Remove) — deletes a file. Use `rm -r` for folders.

## Query / Code Blocks

```bash
# Create a folder
mkdir my-project

# Create an empty file
touch notes.txt

# Copy a file
cp original.txt copy.txt

# Move / rename a file
mv old-name.txt new-name.txt

# Delete a file
rm unwanted.txt

# Delete a folder and everything inside it (be careful)
rm -r old-folder
```

## Performance / Optimization Notes

- `rm` does not move files to a trash. Once deleted, they are hard to recover. Double-check before pressing Enter.
- Use `cp -r` to copy folders. Without `-r`, `cp` only copies individual files.
- `touch` is also useful to update a file's modification time without changing its content.
