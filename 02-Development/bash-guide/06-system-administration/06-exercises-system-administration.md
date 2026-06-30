# Bash System Administration: Exercises

## Architecture / Rationale

These exercises practice reading and changing permissions. Work with test files, not real system files.

## Query / Code Blocks

```bash
# Exercise 1: Create a file and view its permissions with `ls -l`.
# Exercise 2: Create a script that prints "hello". Try to run it. Why does it fail?
# Exercise 3: Add execute permission to your script and run it again.
# Exercise 4: Create a file and remove read permission for others. Ask a friend to read it.
# Exercise 5: Change the permissions of a file to 600. Who can access it now?
# Exercise 6: Create a folder and set its permissions to 755. Can you `cd` into it?
# Exercise 7: Set permissions to 644. Can you `cd` into the folder now? Why not?
# Exercise 8: Check your current umask. Create a file and verify it matches.
# Exercise 9: Use `sudo` to list the contents of /root (requires sudo access).
# Exercise 10: Run `sudo -l` to see what commands you are allowed to run as root.
```

## Performance / Optimization Notes

- Exercise 2: a new file does not have execute permission. You must add it with `chmod +x`.
- Exercise 7: folders need execute permission to be entered. Read (`r`) alone is not enough.
- Exercises 9-10 require a system where you have sudo access. Skip them if you are on a shared server without sudo.
