# Bash Processes: Processes

## Architecture / Rationale

A process is a running program. Every time you run a command, Bash starts a new process. Understanding processes helps you monitor and control what is running.

Key commands:
- `ps` — list running processes.
- `top` or `htop` — interactive process viewer.
- `kill` — send a signal to a process (usually to stop it).
- `pgrep` — find a process by name.

## Query / Code Blocks

```bash
# List your processes
ps

# List all processes on the system
ps aux

# Interactive process viewer (press q to quit)
top

# Find a process by name
pgrep firefox

# Stop a process by PID
kill 12345

# Force-stop a stuck process
kill -9 12345

# Stop a process by name
pkill firefox
```

## Performance / Optimization Notes

- `ps aux` is the classic command to see everything running. The `a` shows all users, `u` shows the user column, `x` shows processes without a terminal.
- `htop` is a friendlier version of `top`. Install it with your package manager if it is not available.
- Try `kill` before `kill -9`. The `-9` signal forces termination and does not let the program clean up.
