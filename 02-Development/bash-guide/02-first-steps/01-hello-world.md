# Bash First Steps: Hello World

## Architecture / Rationale

The "Hello World" of Bash is the simplest possible command: print text to the terminal with `echo`. It confirms your shell is working and you know how to run a command.

- `echo` prints whatever you give it to the terminal output.
- Press Enter to run the command. The shell reads the line, runs the program, and shows the result.

## Query / Code Blocks

```bash
# Your first Bash command
echo "Hello, World!"

# echo works without quotes too (but quotes are safer)
echo Hello World

# Print multiple things
echo "Welcome to" "the Bash guide"
```

## Performance / Optimization Notes

- Use double quotes around text with spaces. Without quotes, each word becomes a separate argument.
- `echo` is built into Bash. It does not start a separate program, so it is very fast.
- Single quotes (`'text'`) and double quotes (`"text"`) work differently. Single quotes prevent variable expansion. Learn this later when you use variables.
