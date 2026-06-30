# Bash System Administration: Anatomy of Permissions

## Architecture / Rationale

The permission string from `ls -l` packs a lot of information into 10 characters. Learning to read it quickly is an essential skill.

The 10-character string:
- Character 1: file type (`-` = file, `d` = directory, `l` = symlink).
- Characters 2-4: owner permissions (`rwx`).
- Characters 5-7: group permissions (`r-x`).
- Characters 8-10: others permissions (`r--`).

## Query / Code Blocks

```bash
# Example permission strings
# -rw-r--r--   regular file, owner can read/write, group and others can read
# drwxr-xr-x   directory, owner has full access, group and others can enter and list
# -rwx------   file, only the owner can read, write, and execute
# -rw-rw-r--   file, owner and group can read/write, others can only read
# lrwxrwxrwx   symbolic link (the permissions shown are not the real ones)

# See permissions of a specific file
ls -l file.txt

# See permissions of all files in a folder
ls -la ~/Documents
```

## Performance / Optimization Notes

- The first character is the file type, not a permission. `-` for regular file, `d` for directory, `l` for link.
- `r`, `w`, `x` are always in the same order. A `-` means the permission is missing: `r-x` means read and execute, no write.
- Permissions can also be represented as numbers (octal). `rwx` = 7, `rw-` = 6, `r--` = 4. `755` = `rwxr-xr-x`.
