# Bash File Management: Unix File System

## Architecture / Rationale

The Unix file system is a tree with a single root. Everything starts at `/`. There are no drive letters like in Windows.

Key folders at the root:
- `/home` — user personal folders (like `C:\Users` in Windows).
- `/etc` — system configuration files.
- `/usr` — user programs and libraries.
- `/var` — variable data like logs.
- `/tmp` — temporary files (cleared on reboot).
- `/bin`, `/sbin` — essential programs.

## Query / Code Blocks

```bash
# See the root of the file system
ls /

# See your home folder
ls ~

# See system configuration
ls /etc

# Check available disk space
df -h

# Check space used by a folder
du -sh ~/Documents
```

## Performance / Optimization Notes

- Everything in Unix is a file — even devices and network sockets. This makes the file system the universal interface.
- Avoid putting files directly in `/`. Work in `/home/yourname/` or `/tmp/` for experiments.
- `df -h` and `du -sh` are the two commands to check disk space. Learn them early.
- For a complete reference of all standard Linux folders, see [[01-Systems/linux-fhs-reference]].
