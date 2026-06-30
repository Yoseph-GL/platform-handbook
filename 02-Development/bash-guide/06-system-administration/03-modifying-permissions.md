# Bash System Administration: Modifying Permissions

## Architecture / Rationale

`chmod` changes file permissions. You can use either symbolic mode (letters) or numeric mode (octal numbers).

- **Symbolic mode**: `u` (user), `g` (group), `o` (others), `a` (all). Add with `+`, remove with `-`, set with `=`.
- **Numeric mode**: three digits. Owner, group, others. Each digit is 4 (read) + 2 (write) + 1 (execute).

## Query / Code Blocks

```bash
# Symbolic mode examples
chmod u+x script.sh       # Add execute for owner
chmod g-w file.txt        # Remove write for group
chmod o+r file.txt        # Add read for others
chmod a+x script.sh       # Add execute for everyone
chmod u=rwx,g=rx,o= file  # Owner rwx, group rx, others nothing

# Numeric mode examples
chmod 755 script.sh       # rwxr-xr-x (standard for scripts)
chmod 644 file.txt        # rw-r--r-- (standard for data files)
chmod 600 secret.key      # rw------- (private file)
chmod 777 public.sh       # rwxrwxrwx (⚠️ never use 777)

# Change owner and group
chown user:group file.txt
```

## Performance / Optimization Notes

- `755` is the standard permission for executable files and folders. `644` is standard for data files.
- Never use `777`. It lets anyone on the system modify your file. If something "needs 777", the problem is elsewhere.
- `chmod +x` is the command you will use most often. It makes a script executable.
