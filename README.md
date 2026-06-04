# Platform Engineering Handbook: Documentation as Code

## Architecture

Documentation-as-code knowledge base for Platform Engineering and DataOps, organized across four operational domains. All content follows the governance spec in [`.readmeAI`](./.readmeAI).

## Repository Map

- `01-Systems` — Linux/Ubuntu internals, TCP/IP, DNS, security hardening
- `02-Development` — Java OOP, Python, data structures, SQL optimization
- `03-Infrastructure` — Docker, orchestration, CI/CD principles
- `04-Operations` — LTS-ready scripts and SOPs for production operations

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
