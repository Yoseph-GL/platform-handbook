# 04-Operations

## Architecture

Canonical domain for production-ready LTS operations scripts and standard operating procedures.

## Scope

- Safe automation scripts with deterministic execution controls
- Operational runbooks for incident response and service verification
- Long-term support patterns for maintainable platform operations

## LTS Script Targets

- `net-debug`
- `docker-net-audit`

## Prerequisites

- Bash 5.x
- Core Linux utilities (`ip`, `ss`, `iptables`)
- Docker Engine (for container-aware scripts)

## Quickstart

```bash
# All scripts default to dry-run
./script-name.sh

# Pass --run to execute system-modifying operations
./script-name.sh --run
```
