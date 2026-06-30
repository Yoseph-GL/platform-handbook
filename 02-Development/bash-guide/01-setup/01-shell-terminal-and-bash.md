# Bash Setup: Shell, Terminal and Bash

## Architecture / Rationale

A shell is a program that reads your commands and tells the operating system to run them. A terminal is the window where you type. Bash is one specific shell (the most common one on Linux and macOS).

Key facts:
- The **terminal** is the application you open (like Terminal.app, Windows Terminal, or Warp).
- The **shell** is the program running inside it (Bash, Zsh, Fish).
- **Bash** stands for Bourne Again SHell. It is the default on most Linux systems.

## Query / Code Blocks

```bash
# Check which shell you are running
echo $SHELL

# Check the Bash version
bash --version
```

## Performance / Optimization Notes

- Bash is the most portable shell. Scripts written in Bash run on almost every Unix system.
- Your terminal and your shell are separate things. You can change either one independently.
- Learn one shell well before trying others. Bash is the best starting point.
