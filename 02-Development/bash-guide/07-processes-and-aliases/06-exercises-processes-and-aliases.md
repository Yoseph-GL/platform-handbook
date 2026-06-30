# Bash Processes and Aliases: Exercises

## Architecture / Rationale

These exercises practice managing processes, using history, and creating aliases.

## Query / Code Blocks

```bash
# Exercise 1: Run `sleep 30 &` to start a background job. List it with `jobs`.
# Exercise 2: Start two `sleep` commands in the background. Wait for both with `wait`.
# Exercise 3: Run `ps aux` and find the Bash processes.
# Exercise 4: Start `top`, sort by memory usage (press `M`), and find the top process.
# Exercise 5: Use `Ctrl+R` to search your history for a command you ran earlier.
# Exercise 6: Use `!!` to repeat the last command.
# Exercise 7: Create an alias `ll` that runs `ls -la`.
# Exercise 8: Add the alias to your `~/.bashrc` so it persists after closing the terminal.
# Exercise 9: Create an alias `..` that goes up one folder. Test it.
# Exercise 10: List all your aliases. Remove one with `unalias` and confirm it is gone.
```

## Performance / Optimization Notes

- For exercise 8, open `~/.bashrc` in Nano or Vim, add the line, save, and run `source ~/.bashrc` to apply.
- Aliases only work in interactive shells. If your alias does not work in a script, that is expected.
- Create 3-5 aliases for your most-used commands. More than 10 and you will forget some.
