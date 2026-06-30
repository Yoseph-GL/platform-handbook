# Bash Logic: Functions

## Architecture / Rationale

A function is a named block of code you can call from anywhere in your script. Functions make scripts modular and reusable.

- Define with `function_name() { ... }` or `function function_name { ... }`.
- Call by name like any other command.
- Arguments work like script arguments: `$1`, `$2` inside the function.
- `local` variables stay inside the function.

## Query / Code Blocks

```bash
#!/bin/bash

# Define a function
greet() {
    local name=$1
    echo "Hello, $name!"
}

# Function with return value
is_even() {
    local num=$1
    if (( num % 2 == 0 )); then
        return 0  # success (true)
    else
        return 1  # failure (false)
    fi
}

# Call the function
greet "Alice"

# Use return value
if is_even 42; then
    echo "42 is even"
else
    echo "42 is odd"
fi
```

## Performance / Optimization Notes

- Use `local` for variables inside functions. Without it, variables leak to the rest of the script.
- Functions must be defined before they are called. Put all functions at the top of your script.
- Return values are 0 for success, non-zero for failure. They are status codes, not data. Use `echo` to return data.
