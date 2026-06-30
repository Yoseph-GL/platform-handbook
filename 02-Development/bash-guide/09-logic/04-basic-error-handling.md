# Bash Logic: Basic Error Handling

## Architecture / Rationale

Error handling makes scripts safe. A script should check if commands succeed and act accordingly. Silent failures cause hard-to-find bugs.

Error handling patterns:
- `set -e` — exit the script immediately if any command fails.
- `set -u` — exit if an undefined variable is used.
- `set -o pipefail` — catch errors in the middle of a pipe.
- Check `$?` after a command to see its exit status (0 = success).

## Query / Code Blocks

```bash
#!/bin/bash
set -euo pipefail  # Safe defaults

# Check if a file exists before using it
if [ ! -f "config.txt" ]; then
    echo "Error: config.txt not found" >&2
    exit 1
fi

# Check command success
mkdir -p /tmp/myapp
if [ $? -ne 0 ]; then
    echo "Error: could not create directory" >&2
    exit 1
fi

# Trap errors for cleanup
cleanup() {
    echo "Cleaning up..."
    rm -f /tmp/myapp/temp.txt
}
trap cleanup EXIT

echo "Script completed successfully."
```

## Performance / Optimization Notes

- `set -euo pipefail` at the top of every script prevents common mistakes. It is the Bash equivalent of a safety belt.
- `$?` holds the exit status of the last command. Check it after commands that can fail.
- Send error messages to standard error with `>&2`. It separates errors from normal output.
