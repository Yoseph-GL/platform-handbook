# Bash Advanced Commands: Exercises

## Architecture / Rationale

These exercises combine reading, searching, pipes, and redirections. You will use multiple commands together.

## Query / Code Blocks

```bash
# Exercise 1: Use `cat` to print a file, then use `less` to scroll through it.
# Exercise 2: Show the first 5 lines of /etc/passwd.
# Exercise 3: Show the last 3 lines of a log file.
# Exercise 4: Count how many lines are in /etc/passwd.
# Exercise 5: Search for your username in /etc/passwd using grep.
# Exercise 6: List all files in /etc, then pipe the output to grep to find files with "conf" in the name.
# Exercise 7: Save the output of `ls -la ~` to a file called "home-listing.txt".
# Exercise 8: Count how many files and folders are in your home folder (hint: pipe ls to wc).
# Exercise 9: Print your PATH variable. Count how many folders are in it (hint: replace : with newline).
# Exercise 10: Follow a log file with `tail -f` while you run another command in a second terminal.
```

## Performance / Optimization Notes

- For exercise 6, the pipe `|` passes the output of `ls` directly to `grep` without a file.
- For exercise 9, use `echo $PATH | tr ':' '\n' | wc -l` to count PATH folders.
- Exercises 1-5 use single commands. Exercises 6-10 combine two or more with pipes.
