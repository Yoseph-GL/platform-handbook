# Bash Processes: Jobs

## Architecture / Rationale

Jobs let you run multiple commands in one terminal. You can start a command in the background, check its status, and bring it back to the foreground.

- `&` at the end of a command runs it in the background.
- `jobs` lists background jobs in this terminal.
- `fg` brings a job to the foreground.
- `bg` resumes a paused job in the background.
- `Ctrl+Z` pauses the current foreground job.

## Query / Code Blocks

```bash
# Run a command in the background
sleep 60 &

# List background jobs
jobs

# Bring job #1 to the foreground
fg %1

# Pause the current job (Ctrl+Z), then resume in background
bg

# Run a long task in the background and disconnect it
nohup long-task &
```

## Performance / Optimization Notes

- Use `&` for commands that take a long time (downloads, builds, file processing). You can keep working while they run.
- `jobs` only shows jobs from your current terminal. A job in another terminal does not appear.
- `nohup` protects a background job from being killed when you close the terminal.
