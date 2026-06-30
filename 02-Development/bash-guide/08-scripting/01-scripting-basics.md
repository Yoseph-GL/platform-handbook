# Bash Scripting: Scripting Basics

## Architecture / Rationale

A shell script is a text file with a list of commands. You make it executable and run it like any other program.

Script structure:
- Line 1: `#!/bin/bash` (the shebang).
- Lines 2+: Bash commands, one per line or separated by `;`.
- Comments start with `#` (except the shebang).

## Query / Code Blocks

```bash
#!/bin/bash
# My first script

echo "Starting the script..."
echo "Today is $(date)"
echo "You are logged in as $USER"
echo "Script finished."
```

## Performance / Optimization Notes

- Always use `#!/bin/bash` as the first line. Without it, the script might run under a different shell.
- Make your script executable with `chmod +x script.sh`, then run it with `./script.sh`.
- Use comments (`#`) to explain what your script does. Future you will thank present you.
