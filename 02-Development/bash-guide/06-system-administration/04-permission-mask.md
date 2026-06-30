# Bash System Administration: Permission Mask

## Architecture / Rationale

`umask` sets the default permissions for new files and folders you create. It subtracts permissions from a base value to prevent files from being too open by default.

- Default base: files start at `666` (rw-rw-rw-), folders at `777` (rwxrwxrwx).
- The umask value is subtracted from the base.
- Common umask: `022` → files get `644` (rw-r--r--), folders get `755` (rwxr-xr-x).

## Query / Code Blocks

```bash
# Show current umask value
umask

# Show in symbolic form
umask -S

# Set a new umask (temporary, for this session)
umask 022

# Common umask values:
# 022 - owner full access, group and others read (safe default)
# 002 - owner and group full access, others read (good for shared projects)
# 077 - owner full access, no access for anyone else (private files)
```

## Performance / Optimization Notes

- The default umask on most systems is `022` or `002`. You rarely need to change it.
- Set your umask in `~/.bashrc` if you need a permanent change. Do not set it in every terminal session.
- A umask of `077` is good for sensitive files (SSH keys, passwords). You set it before creating those files.
