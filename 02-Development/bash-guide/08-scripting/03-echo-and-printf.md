# Bash Scripting: Echo and Printf

## Architecture / Rationale

`echo` and `printf` are the two commands for printing output in Bash. `echo` is simpler. `printf` gives you more control over formatting.

- `echo` — prints text followed by a newline. Use `-n` to skip the newline.
- `printf` — prints formatted text like C's `printf()`. No automatic newline. Use `\n` for newlines.
- `printf` is more portable across systems. `echo` behavior can vary slightly.

## Query / Code Blocks

```bash
#!/bin/bash

# Echo: simple output
echo "Hello, world"
echo -n "No newline at the end"

# Printf: formatted output
printf "Hello, %s\n" "world"
printf "Number: %d, Float: %.2f\n" 42 3.14159

# Printf with multiple arguments
printf "%s is %d years old.\n" "Alice" 25 "Bob" 30

# Table with printf
printf "%-20s %10s\n" "Name" "Score"
printf "%-20s %10d\n" "Alice" 95
printf "%-20s %10d\n" "Bob" 87
```

## Performance / Optimization Notes

- Use `echo` for simple output. Use `printf` when you need alignment, decimals, or specific formatting.
- `printf` does not add a newline automatically. Add `\n` at the end of your format string.
- `echo` is faster than `printf` for simple text. The difference only matters in loops with thousands of iterations.
