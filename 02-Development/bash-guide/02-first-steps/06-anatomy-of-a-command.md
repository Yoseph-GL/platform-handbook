# Bash First Steps: Anatomy of a Command

## Architecture / Rationale

Every Bash command follows the same structure. Understanding this pattern helps you read and write any command.

Parts of a command:
- **Command**: the program to run (`ls`, `cd`, `grep`).
- **Options / Flags**: modify how the command works. Short flags start with `-` (`-l`), long flags start with `--` (`--all`).
- **Arguments**: the targets of the command (files, folders, text).

## Query / Code Blocks

```bash
# Command without options or arguments
pwd

# Command with an option (list in long format)
ls -l

# Command with a long option
ls --all

# Command with option and argument
ls -l /home/user/Documents

# Multiple options combined
ls -la

# Full pattern: command -options --long-options arguments
grep -i --color "error" log.txt
```

## Performance / Optimization Notes

- Short options can be combined: `ls -l -a` equals `ls -la`.
- Long options (`--help`) are more readable in scripts. Short options (`-h`) are faster for interactive use.
- Every command has its own set of options. `ls` and `grep` do not share them. Check with `--help` or `man`.
