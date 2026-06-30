# Bash Scripting: Exercises

## Architecture / Rationale

These exercises guide you through writing your first scripts. Start simple and add features.

## Query / Code Blocks

```bash
# Exercise 1: Write a script that prints "Hello, Bash!" and make it executable.
# Exercise 2: Write a script that asks for the user's name and greets them.
# Exercise 3: Write a script that takes two numbers as arguments and prints their sum.
# Exercise 4: Write a script that lists all files in a folder given as an argument.
# Exercise 5: Write a script that prints a formatted table of your aliases.
# Exercise 6: Write a script that reads a filename and prints how many lines it has.
# Exercise 7: Write a script that takes a name and age, then prints a message 5 years in the future.
```

## Performance / Optimization Notes

- Start each script with `#!/bin/bash` and make it executable (`chmod +x`).
- Test your scripts with edge cases: no arguments, spaces in arguments, empty input.
- For exercise 3, use `$(( $1 + $2 ))` to do arithmetic in Bash.
