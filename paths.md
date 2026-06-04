# Linux Filesystem Hierarchy and Docker Persistence

## Architecture / Rationale

A deterministic understanding of the Linux Filesystem Hierarchy Standard (FHS) is mandatory for backend infrastructure, state management, and debugging. System state must be strictly separated from ephemeral runtimes, especially when operating containerized workloads.

## Reference Tables

### Core Linux FHS

| Path | Contents | Operational Use Case |
| :--- | :--- | :--- |
| `/` | System root | Absolute starting point for all paths. |
| `/bin` | Basic user commands | Essential executables (`ls`, `cp`, `bash`). |
| `/sbin` | Basic admin commands | Critical system administration tools. |
| `/usr/bin` | Installed binaries | Standard commands for daily operational use. |
| `/usr/sbin` | Installed admin binaries | System and network service executables. |
| `/usr/local/bin` | Manually installed binaries | Global tools built or installed locally. |
| `/usr/local/sbin` | Manual admin binaries | Global administration scripts. |
| `~/.local/bin` | User binaries/scripts | Primary location for isolated personal scripts. |
| `/lib`, `/lib64` | Critical system libraries | Do not modify manually; dependencies for `/bin`. |
| `/usr/lib` | App/package libraries | Shared objects and plugins for installed software. |
| `/usr/share` | Non-binary data | Architecture-independent assets and documentation. |
| `/etc` | Global system configuration | Core settings for services and host behavior. |
| `~/.config` | User-level configuration | Local application settings (e.g., Kitty, Zsh). |
| `/etc/systemd/system` | Global systemd units | Service creation and system overrides. |
| `~/.config/systemd/user`| User systemd units | Daemon definitions for rootless execution. |
| `/var` | Variable data | Root directory for dynamic state. |
| `/var/log` | System logs | Primary target for diagnostics and troubleshooting. |
| `/var/lib` | Persistent service state | Data for databases, Docker, and system services. |
| `/run` | Ephemeral RAM state | PIDs, sockets, and runtime tracking. |
| `/tmp` | Short-lived temporaries | High-speed, volatile files (cleared on reboot). |
| `/var/tmp` | Persistent temporaries | Temporary files that must survive a reboot. |
| `/home` | Standard user space | Personal projects, workspaces, and dotfiles. |
| `/root` | Admin home directory | Isolated workspace for root operations. |
| `/boot` | Kernel and initramfs | Critical bootloader components. |
| `/boot/efi` | EFI partition | UEFI bootloader execution path. |
| `/dev` | System devices | Block devices, TTY, and hardware interfaces. |
| `/proc` | Virtual kernel info | Live inspection of system processes and memory. |
| `/sys` | Virtual hardware state | Interaction with kernel device drivers. |
| `/opt` | Third-party applications | Self-contained, monolithic software packages. |
| `/snap` | Snap runtime mounts | Read-only binaries for Snap packages. |
| `/var/snap` | Snap persistent data | Configuration and state for Snap applications. |
| `/mnt` | Temporary manual mounts | Diagnostics and testing of external filesystems. |
| `/media` | Auto-mounted media | Removable storage (USB, external drives). |

### Docker Persistence Layer

| Path | Definition |
| :--- | :--- |
| `/var/lib/docker` | Canonical data root for the Docker daemon. |
| `/var/lib/docker/volumes/<vol>/_data` | Physical host path for managed named volumes. |
| `/var/lib/docker/containers` | Container metadata, configuration, and raw logs. |
| `./path:/container-path` | Bind mount syntax: Maps local workspace directly to container. |

## Operational Commands

```bash
# Locate binaries and trace execution paths
echo $PATH               # Output the directories the shell searches for executables
type -a <cmd>            # Reveal all instances of a command (aliases, functions, binaries)
which <cmd>              # Output the absolute path of the first executable found
dpkg -S /usr/bin/<cmd>   # Identify the Debian/Ubuntu package that owns a specific binary
