# Bash Scripting: Reading Data

## Architecture / Rationale

The `read` command gets input from the user while a script is running. It makes scripts interactive.

- `read variable` — waits for the user to type something and press Enter. The input is stored in the variable.
- `read -p "prompt" variable` — shows a prompt before reading.
- `read -s variable` — hides the input (useful for passwords).

## Query / Code Blocks

```bash
#!/bin/bash

# Ask for the user's name
read -p "What is your name? " name
echo "Hello, $name!"

# Read multiple values
read -p "Enter first and last name: " first last
echo "First: $first, Last: $last"

# Read a password (input hidden)
read -sp "Enter password: " password
echo
echo "Password saved."
```

## Performance / Optimization Notes

- Use `-p` instead of a separate `echo` command. It keeps the prompt and input on the same line.
- `read` without a variable stores the input in `$REPLY`. Use it for quick one-off reads.
- Always quote variables: `"$name"`. If the user types spaces, the variable still works correctly.
