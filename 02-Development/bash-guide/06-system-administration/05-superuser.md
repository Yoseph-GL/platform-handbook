# Bash System Administration: Superuser

## Architecture / Rationale

The superuser (root) has full control over the system. `sudo` lets you run specific commands as root without logging in as root.

- `sudo <command>` — runs a command as root.
- `sudo -i` or `sudo su -` — opens a root shell.
- Only users in the `sudo` group can use `sudo`.

## Query / Code Blocks

```bash
# Run a command as root
sudo apt update

# Edit a system file as root
sudo nano /etc/nginx/nginx.conf

# Become root (interactive shell)
sudo -i

# Run a command as a different user
sudo -u username command

# Check what sudo can do for your user
sudo -l
```

## Performance / Optimization Notes

- Use `sudo` for specific commands, not for everything. A root shell (`sudo -i`) should be temporary.
- Always double-check a `sudo rm` or `sudo chmod` command before pressing Enter. There is no undo.
- `sudo` logs all commands to `/var/log/auth.log`. You can see who ran what and when.
