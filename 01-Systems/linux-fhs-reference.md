# Systems: Linux Filesystem Hierarchy Reference

## Architecture / Rationale

The Linux Filesystem Hierarchy Standard (FHS) defines where files and folders go. Knowing the standard folders helps you find files, debug problems, and organize your own projects.

Key principles:
- System files and user files live in separate places. Do not mix them.
- Configuration goes in `/etc`. Variable data (logs, databases) goes in `/var`.
- Your personal files belong in `/home/yourname`. Your personal scripts go in `~/.local/bin`.

## Query / Code Blocks

```bash
# Core system folders
# /bin       — basic user commands (ls, cp, bash)
# /sbin      — system administration commands
# /usr/bin   — installed programs
# /usr/local/bin — programs you install manually
# ~/.local/bin   — your personal scripts

# Configuration
# /etc           — system-wide configuration
# ~/.config      — your personal application settings

# Variable data
# /var/log       — system logs (check here first when debugging)
# /var/lib       — persistent data for services (databases, Docker)
# /run           — temporary runtime data (cleared on reboot)
# /tmp           — short-lived temporary files (cleared on reboot)
# /var/tmp       — temporary files that survive a reboot

# User spaces
# /home          — all user home folders
# /root          — root user's home folder

# System information (virtual filesystems)
# /proc          — live process and memory info
# /sys           — hardware and kernel info
# /dev           — device files (disks, terminals)

# Other important folders
# /boot          — kernel and boot files
# /opt           — third-party applications
# /mnt           — temporary manual mounts
# /media         — auto-mounted removable drives (USB sticks)

# Docker persistence
# /var/lib/docker                    — Docker's data root
# /var/lib/docker/volumes/<name>/_data — named volume data on the host
# /var/lib/docker/containers          — container configs and logs
```

## Performance / Optimization Notes

- Use `~/.local/bin` for your own scripts. It keeps them separate from system programs.
- Check `/var/log` first when something breaks. Most services write their errors there.
- `/tmp` is cleared on every reboot. Do not store anything important there. Use `/var/tmp` for files that must persist.
- Docker volumes are at `/var/lib/docker/volumes/`. Back up this folder to save your container data.
- The `file` command tells you what type a file is. Use it before opening unknown files.

[[02-Development/bash-guide/03-file-management/01-unix-file-system]]
