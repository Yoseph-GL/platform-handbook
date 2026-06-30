# Platform Engineering Handbook: Documentation as Code

## Architecture

Documentation-as-code knowledge base for Platform Engineering and DataOps, organized across four operational domains.

## Repository Map

- `01-Systems` — Linux/Ubuntu internals, TCP/IP, DNS, security hardening, filesystem reference
- `02-Development` — SQL, Bash/Shell scripting, HTML/CSS, and Git learning guides
- `03-Infrastructure` — Docker, orchestration, CI/CD principles
- `04-Operations` — LTS-ready scripts and SOPs for production operations

## Learning Guides

- [SQL Guide](./02-Development/sql-guide/00-index.md) — from schema design to advanced queries
- [HTML/CSS Guide](./02-Development/html-css-guide/00-index.md) — from basic tags to CSS Grid and animations
- [Bash Guide](./02-Development/bash-guide/00-index.md) — from terminal basics to scripting and cron jobs
- [Git Guide](./02-Development/git-guide/00-index.md) — commit conventions and collaboration patterns

## Prerequisites

- Git
- Markdown editor (VS Code, Obsidian, or equivalent)

## Quickstart

```bash
git clone git@github.com:Yoseph-GL/documentation-as-code.git
cd documentation-as-code
```

## LTS Script Standard

All automation scripts and code snippets in this repository enforce `set -euo pipefail`, use absolute path anchoring, and require the `--run` flag for system-modifying execution. Dry-run is the default when `--run` is absent.
