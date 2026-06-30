# Bash Logic: Conditionals

## Architecture / Rationale

Conditionals let your script make decisions. The `if` statement runs different code depending on whether a condition is true or false.

- `if [ condition ]; then ... fi` — basic conditional.
- `elif` — else-if for multiple branches.
- `else` — catch-all when no condition is true.
- Use `test` or `[ ]` to check conditions. `[[ ]]` is the modern, safer version.

## Query / Code Blocks

```bash
#!/bin/bash

# Basic if statement
if [ "$1" = "hello" ]; then
    echo "You said hello!"
fi

# If-else
age=$1
if [ "$age" -ge 18 ]; then
    echo "You are an adult."
else
    echo "You are a minor."
fi

# If-elif-else
score=$1
if [ "$score" -ge 90 ]; then
    echo "Grade: A"
elif [ "$score" -ge 80 ]; then
    echo "Grade: B"
elif [ "$score" -ge 70 ]; then
    echo "Grade: C"
else
    echo "Grade: F"
fi
```

## Performance / Optimization Notes

- Spaces inside `[ ]` are required. `[ "$a" = "$b" ]` works. `["$a"="$b"]` does not.
- Use `[[ ]]` instead of `[ ]` in Bash scripts. It handles empty variables and spaces safely.
- Common conditions: `-eq` (equal), `-ne` (not equal), `-lt` (less than), `-gt` (greater than), `-f` (is file), `-d` (is directory).
