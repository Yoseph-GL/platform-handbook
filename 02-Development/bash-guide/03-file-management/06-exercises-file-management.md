# Bash File Management: Exercises

## Architecture / Rationale

These exercises practice file operations, wildcards, and listing commands. Complete them in order.

## Query / Code Blocks

```bash
# Exercise 1: Create a folder structure: project/{src,docs,data} in one command.
# Exercise 2: Create three .txt files named "a.txt", "b.txt", "c.txt" in project/.
# Exercise 3: List only the .txt files using a wildcard.
# Exercise 4: List all files sorted by size, largest first.
# Exercise 5: List all files including hidden ones, with human-readable sizes.
# Exercise 6: Copy all .txt files to the "docs" folder using a wildcard.
# Exercise 7: Move "a.txt" to "data/" and rename it to "alpha.txt" in one command.
# Exercise 8: Use the `file` command on a .txt file, a folder, and /bin/ls.
# Exercise 9: List the /etc folder and find at least 3 folders you recognize.
# Exercise 10: Check disk space on your system with `df -h`.
```

## Performance / Optimization Notes

- For exercise 1, remember the `-p` flag with `mkdir`.
- For exercise 8, notice that `/bin/ls` is a binary executable while a `.txt` file is plain text.
- After completing these exercises, clean up by deleting the `project/` folder with `rm -r`.
