# Bash Level 6: System Administration

## Architecture / Rationale

This level covers file permissions and user management. Permissions control who can read, write, and execute files. This is the foundation of Unix security.

Scope:
- Types of permissions and the user categories.
- How to read permission strings (`-rwxr-xr--`).
- Changing permissions with `chmod`.
- The permission mask (`umask`) for new files.
- Running commands as the superuser with `sudo`.

## Query / Code Blocks

```bash
# Module pages
# [[01-types-of-permissions-and-users]]
# [[02-anatomy-of-permissions]]
# [[03-modifying-permissions]]
# [[04-permission-mask]]
# [[05-superuser]]
# [[06-exercises-system-administration]]
```

## Performance / Optimization Notes

- Permissions protect your files from accidental changes and malicious access. Learn them before you need them.
- Use `sudo` only when necessary. Running everything as root is a security risk.
