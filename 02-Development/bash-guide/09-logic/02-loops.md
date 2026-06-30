# Bash Logic: Loops

## Architecture / Rationale

Loops repeat a block of code. Use a loop when you need to do the same thing to many files, lines, or values.

- `for variable in list; do ... done` — iterates over a list.
- `while [ condition ]; do ... done` — repeats while a condition is true.
- `until [ condition ]; do ... done` — repeats until a condition becomes true.
- `break` exits the loop early. `continue` skips to the next iteration.

## Query / Code Blocks

```bash
#!/bin/bash

# For loop: iterate over a list
for name in Alice Bob Charlie; do
    echo "Hello, $name!"
done

# For loop: iterate over files
for file in *.txt; do
    echo "Processing $file..."
    wc -l "$file"
done

# C-style for loop
for (( i = 1; i <= 5; i++ )); do
    echo "Iteration $i"
done

# While loop: count down
count=5
while [ $count -gt 0 ]; do
    echo "Countdown: $count"
    count=$((count - 1))
    sleep 1
done
echo "Go!"
```

## Performance / Optimization Notes

- Use `for file in *.txt` to process many files at once. It is cleaner than running a command file by file.
- Avoid `for line in $(cat file)`. It breaks on spaces. Use `while read line; do ... done < file` instead.
- `while true` runs forever. Always have an exit condition or a `break` inside the loop.
