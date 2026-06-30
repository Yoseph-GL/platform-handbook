# Bash Scripting: Arguments and Parameters

## Architecture / Rationale

Scripts can accept arguments from the command line. Inside the script, special variables hold those values.

- `$1`, `$2`, `$3`, ... — the first, second, third argument.
- `$0` — the name of the script itself.
- `$#` — the number of arguments.
- `$@` — all arguments as separate words.
- `$*` — all arguments as a single string.

## Query / Code Blocks

```bash
#!/bin/bash

# Check that arguments were provided
if [ $# -eq 0 ]; then
    echo "Usage: $0 <name> <age>"
    exit 1
fi

name=$1
age=$2

echo "Hello, $name!"
echo "You are $age years old."
echo "Script name: $0"
echo "Number of arguments: $#"

# Loop through all arguments
echo "All arguments:"
for arg in "$@"; do
    echo "  - $arg"
done
```

## Performance / Optimization Notes

- Always check `$#` before using `$1`. If the user provides no arguments, your script should show a helpful message.
- Use `"$@"` (with quotes) to preserve spaces in arguments. `$*` without quotes breaks arguments with spaces.
- Shift through arguments with `shift` when processing many options. It moves `$2` to `$1`, `$3` to `$2`, and so on.
