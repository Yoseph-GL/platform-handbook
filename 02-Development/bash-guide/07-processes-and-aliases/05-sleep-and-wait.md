# Bash Processes: Sleep and Wait

## Architecture / Rationale

`sleep` pauses the shell for a set time. `wait` pauses until a background job finishes. Together they give you basic control over timing in scripts and interactive sessions.

- `sleep <seconds>` — pauses for a number of seconds.
- `sleep 5m` — pauses for 5 minutes (suffixes: `s`, `m`, `h`, `d`).
- `wait` — waits for all background jobs to finish.
- `wait <pid>` — waits for a specific job.

## Query / Code Blocks

```bash
# Pause for 5 seconds
sleep 5

# Pause for 1 minute
sleep 1m

# Start two background jobs, then wait for both
long-task1 &
long-task2 &
wait
echo "Both tasks are done"

# Pause between commands in a sequence
echo "Starting..."
sleep 2
echo "Done."

# Wait for a specific background job
my-script.sh &
PID=$!
echo "Waiting for script to finish..."
wait $PID
echo "Script finished"
```

## Performance / Optimization Notes

- `sleep` is precise enough for scripts but not for real-time applications. Do not use it for sub-second timing in production.
- `wait` without arguments waits for ALL background jobs. Use `wait $PID` to wait for a specific one.
- Combine `sleep` and `wait` in startup scripts to ensure services start in the right order.
