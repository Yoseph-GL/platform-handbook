# Documentation as Code

## Architecture

Personal knowledge base built with Markdown and Git. I write down what I
learn so I can find it years from now — structured, searchable, and
version-controlled.

Every note follows the same three-part format: why it matters, how to use
it, and how to not mess it up. The goal is retention through writing, not
just reading.

## Repository Map

- `01-Systems` — Linux/Ubuntu internals, TCP/IP, DNS, security, filesystem
- `02-Development` — SQL, Bash, HTML/CSS, and Git learning guides
- `03-Infrastructure` — Docker, orchestration, CI/CD *(planned)*
- `04-Operations` — LTS scripts and SOPs *(planned)*

## Learning Guides

- [SQL Guide](./02-Development/sql-guide/00-index.md) — schema design to advanced queries
- [HTML/CSS Guide](./02-Development/html-css-guide/00-index.md) — basic tags to CSS Grid and animations
- [Bash Guide](./02-Development/bash-guide/00-index.md) — terminal basics to scripting and cron
- [Git Guide](./02-Development/git-guide/00-index.md) — commit conventions and collaboration patterns

## Related Projects

Projects where I apply what I document here:

- [Auth Registration Challenge](https://github.com/Yoseph-GL/auth-registration-challenge) — Django 5.2 + PostgreSQL 16 + Docker Compose
- [ops-docker-databases](https://github.com/Yoseph-GL/ops-docker-databases) — homelab sandbox on Ubuntu Server 24.04
- [ubuntu-ops-dotfiles](https://github.com/Yoseph-GL/ubuntu-ops-dotfiles) — Bash automation for safe updates and backups
- [RacingCars](https://github.com/Yoseph-GL/RacingCars) — OOP fundamentals simulator in Java

## Conventions

Every note follows strict formatting rules to stay consistent over time.
See [AGENTS.md](./AGENTS.md) for the full specification.

## Quickstart

```bash
git clone git@github.com:Yoseph-GL/documentation-as-code.git
cd documentation-as-code
```

## LTS Script Standard

All scripts enforce `set -euo pipefail`, use absolute paths, and require
`--run` for system-modifying execution. Dry-run is the default.
