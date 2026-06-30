# Bash First Steps: Orientation Commands

## Architecture / Rationale

Orientation commands tell you where you are and what is around you. They are the first commands to run when you open a terminal in an unfamiliar place.

- `pwd` (Print Working Directory) — shows your current folder path.
- `ls` (List) — shows the files and folders in your current location.
- `whoami` — shows your username.

## Query / Code Blocks

```bash
# Where am I?
pwd

# What is here?
ls

# Who am I logged in as?
whoami

# What is my computer's name?
hostname
```

## Performance / Optimization Notes

- Always run `pwd` before deleting or moving files. It confirms you are in the right folder.
- `ls` without arguments shows the current folder. `ls /path` shows a different folder without moving there.
- These three commands (`pwd`, `ls`, `whoami`) answer the three basic questions of every terminal session.
