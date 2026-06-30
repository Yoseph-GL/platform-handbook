# Bash Logic: Exercises

## Architecture / Rationale

These exercises combine conditionals, loops, and functions into complete scripts.

## Query / Code Blocks

```bash
# Exercise 1: Write a script that takes a number and says if it is positive, negative, or zero.
# Exercise 2: Write a script that prints numbers from 1 to 10 with a for loop.
# Exercise 3: Write a script that loops through all .txt files and counts their lines.
# Exercise 4: Write a function that takes a name and prints "Good morning, <name>!".
# Exercise 5: Write a script that asks for a password and keeps asking until it is correct.
# Exercise 6: Write a script with error handling: check that an argument is provided, show usage if not.
# Exercise 7: Write a script that creates a backup folder and copies all .txt files into it. Use trap for cleanup.
```

## Performance / Optimization Notes

- For exercise 5, use a `while` loop with `read -sp` for hidden password input.
- For exercise 6, check `$#` at the start. Exit with code 1 and a message if it is 0.
- For exercise 7, create the backup in `/tmp/` and use `trap cleanup EXIT` to remove it when the script ends.
