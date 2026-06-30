# Bash Setup: Bash on Windows

## Architecture / Rationale

Windows does not include Bash by default, but you have several ways to run it. The best option today is WSL (Windows Subsystem for Linux).

Options for Bash on Windows:
- **WSL (Windows Subsystem for Linux)**: a full Linux environment inside Windows. Recommended.
- **Git Bash**: comes with Git for Windows. A lighter option for basic commands.
- **Cygwin**: an older compatibility layer. Use WSL instead.

## Query / Code Blocks

```bash
# After installing WSL, open a Linux terminal
wsl

# Check you are running Bash
echo $0
```

## Performance / Optimization Notes

- WSL 2 is faster than WSL 1 for file operations. Upgrade if you are still on WSL 1.
- Git Bash is enough for learning basic commands and running shell scripts.
- Your Windows files are at `/mnt/c/` inside WSL. You can access them from both sides.
